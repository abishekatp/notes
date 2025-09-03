# Rust

- Here I will be trying to explain the core features of the Rust programming language in simple terms. 

- It will not be a in depth explanation of nook and corners of the language. If you are looking for something like that then there are lot of resources for that already. Such as official [Rust book](https://doc.rust-lang.org/book/), [The standard library](https://doc.rust-lang.org/std/index.html), [Cargo book](https://doc.rust-lang.org/cargo/index.html) and there are many other resources which you can find in the [official website](https://www.rust-lang.org/).

- This will be more like a personal notes. Just explaining the bare minimum things that needs to be understood to grasp the core idea of the language. Later if you want to go in depth in any of the language features, you can do that using the above mentioned resources.


# Introduction 

## Why and What is Rust?

- Rust is fully open source(managed by a community) language. And it strives to achieve safety and productivity, speed and ergonomics all at the same time. It is speed for both development and after deployment. It is safe without runtime garbage collection.

- Rust provides the features of low level(system) programming language with flexibility and tools like most modern high level programming language. It has `cargo` the build and dependency management tool, rustfmt for code formatting and rust-analyzer for IDE support and inline error messages.

- Rust ensures memory safety and efficient memory management at compile time using its ownership and borrowing system, eliminating the need for a runtime garbage collector. Because of that it can be used for both system programming and high level application developments(like command line tools, web server, web applications, machine learning, data science and many more).


## How does it differs from major languages like Python, Java, C and C++?

- ***C & C++***: 

- ***Python & Java***: 



## Garbage Collection, Ownership and Lifetimes

- 





## Why do we need smart pointers like Box, Rc, Arc, RefCell?

- Box is mainly used for storing recursive data structure. Using the type itself as a field definition of the same type.

```rs
enum List {
    Cons(i32, List),
    Nil,
}
```
- This has the issue of `infinite size`. Since type is nested inside the type definition computing the size needed to store the object of this particular type becomes infinite.

```rs
enum List {
    Cons(i32, &List),
    Nil,
}
```
- This approach seems like it should work. This approach works well for C or C++. But Rust ownership and lifetime rules does not allow this definition.
- Because if you are refering to some arbitrary List object, then who will be the owner of that inner object. This will interfere with computing the lifetime of the object to drop them when their lifetime ends. 
- So one of the the correct ways to do this is as follows

```rs
enum List {
    Cons(i32, Box<List>),
    Nil,
}
```


## What is `Box<T>`?

- Smart pointer is similar to pointer references, It will have fixed size in memory but it owns the object it is refering to instead of just having its reference.
- Boxes provide only the indirection and heap allocation; they don’t have any other special capabilities, like those we’ll see with the other smart pointer types. The Box<T> type is a smart pointer because it implements the Deref trait, which allows Box<T> values to be treated like references. When a Box<T> value goes out of scope, the heap data that the box is pointing to is cleaned up as well because of the Drop trait implementation.

- So conceptually, the deref method for Box<T> does something similar to below but not exactly the same:
```rs
use std::ops::Deref;

impl<T> Deref for MyBox<T> {
    type Target = T;

    fn deref(&self) -> &Self::Target {
        &self.0
    }
}
```

- So conceptually, the drop method for Box<T> does something like below but not exactly the same:
```rs
impl<T> Drop for MyBox<T> {
    fn drop(&mut self) {
        // (Pseudocode — not actual Rust code)
        // Call `drop` on the value inside the box
        drop(self.value); // drops T
        // Then deallocate the heap memory
        dealloc(self.ptr);
    }
}
```



## What is `Rc<T>`?

Rc<T> is a reference-counted smart pointer. It enables shared ownership of data: multiple `Rc`s can point to the same heap allocation, and the value is dropped only when the last `Rc` goes out of scope. This means each instance of `Rc` owns that chunk of memory in heap unlike references which only point to that memory address.


- ***`Deref` Implementation for `Rc<T>`:*** `Rc<T>` implements `Deref` similarly to `Box<T>`, so you can use it like a regular reference (`&T`). Simplified version:

```rust
use std::ops::Deref;

impl<T: ?Sized> Deref for Rc<T> {
    type Target = T;

    fn deref(&self) -> &Self::Target {
        // Internally Rc holds a pointer to T, like: RcBox<T> { strong, weak, value }
        unsafe { &*self.ptr.as_ref().value.get() }
    }
}
```

Actual implementation involves `NonNull` pointer and interior mutability using `UnsafeCell`. The `.get()` method is from `UnsafeCell`.



- ***`Drop` Implementation for `Rc<T>`:*** When an `Rc<T>` is dropped, it **decrements the strong reference count**. If it reaches zero, the inner value `T` is dropped and memory is deallocated if the weak count is also zero. Simplified idea:

```rust
impl<T> Drop for Rc<T> {
    fn drop(&mut self) {
        // Decrement strong count
        if self.decrement_strong() == 0 {
            // Drop the actual value of T
            unsafe {
                drop_in_place(self.ptr.as_ref().value.get());
            }

            // Decrement weak count
            if self.decrement_weak() == 0 {
                // Free memory if no strong or weak refs left
                dealloc(self.ptr);
            }
        }
    }
}
```

Again, actual code uses atomic or non-atomic reference counting depending on platform/thread-safety needs.

- Example

```rust
use std::rc::Rc;

fn main() {
    let a = Rc::new(String::from("hello"));
    let b = a.clone(); // increases ref count
    println!("{}", a.len()); // Deref<Target = String>
} // ref count drops on scope exit, value dropped only when count reaches 0
```


## Difference between Box<T> and Rc<RefCell<T>>


#### `Rc` and `RefCell` (shared, interior mutable smart pointers)

* When you **clone an `Rc<T>`**, you're cloning the **reference counter**, not the inner data.
  It means **all clones point to the same data** — like a shared pointer.

* `RefCell<T>` allows **interior mutability**, i.e., you can mutate data inside even if the outer structure is immutable, via runtime borrow checking.

✅ So:

```rust
let a = Rc::new(RefCell::new(5));
let b = Rc::clone(&a);
*b.borrow_mut() = 10; // changes value for both `a` and `b`
```

---

### ❌ `Box<T>` (owning, single-owner smart pointer)

* When you **clone a `Box<T>`**, you're cloning the **entire data** that it points to — not the pointer.
* That means a new allocation happens, and you get two **independent** heap-allocated objects.

❌ So:

```rust
let a = Box::new(5);
let b = a.clone(); // deep copy!
*b = 10;
println!("{}", a); // still prints 5
```

---

### In your case with Linked List:

If you do:

```rust
let node1 = Some(Box::new(ListNode { val: 1, next: None }));
let node2 = node1.clone();
```

Then modifying `node2` will **not** affect `node1` — they are two separate lists.

But if you had used:

```rust
let node1 = Rc::new(RefCell::new(ListNode { val: 1, next: None }));
let node2 = Rc::clone(&node1);
node2.borrow_mut().val = 42;
// node1 now sees the updated value
```

---

### ✅ When to use what:

| Use Case                                                  | Use `Box<T>` | Use `Rc<RefCell<T>>`                                   |
| --------------------------------------------------------- | ------------ | ------------------------------------------------------ |
| Ownership-only tree or list (no shared ownership, strict) | ✅            | ❌                                                      |
| Shared access across multiple places                      | ❌            | ✅                                                      |
| Need to mutate through shared references                  | ❌            | ✅                                                      |
| Leetcode-style singly linked list                         | ✅            | ❌ (unless problem needs back-links or multiple owners) |

---

If you want to mutate shared nodes or access the same node from multiple places — go with `Rc<RefCell<T>>`. If you're just building or reversing a strict, owned list — stick with `Box<T>` and use `.take()` to move ownership safely.

Let me know if you want to rewrite your reverse function with `Rc<RefCell>` for experimentation.
