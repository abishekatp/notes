# Arrays Concepts
- The data structure used to store collection of same type of elements in a consecutive memory locations.

## Array Traversal
- **Iteration:** 
    - It is just iterating through elements of an array to compute some value
- **Iteration Patterns:** 
    - It may happen forward, backward, stepping by k, recursively or by nested loops to handle them in pairs.
    - Most of the array problems use this approach like finding Max/Min, counting, searching, sorting or others.
- **Nested Iteration and Alternatives:** 
    - If you need to handle pair of elements, then first think of nested loops
    - As a next step then check whether any better pattern exists. 
    - For e.g two pointers, sliding window, a prefix sums, hashmap, or sorting.

```go
nums := []int{1, 2, 4, 5}
// 1. Forward Iteration
for i := 0; i < len(nums); i++ {
    _ := nums[i]
}

// 1. Forward Iteration using range
for i, v := range nums {
    _ := i
    _ := v
}
```


### Two Pointers
- **Basic Logic:** Use two indeces that iterate through the array using some rule.
- A lot of time it would help replace O(n^2) nested loop logic to O(n) iteration logic.
- **Three Common Forms:** There are three common forms in this kind of logic.
    - **Opposite Ends:** Iterating from the opposite end of the same array. 
    - **Same Direction(Reader/Writer)** Two pointer move in the same direction, but one reads the value and another writes the value.
    - **Fast and Slow** One of the pointers will move fast(increment by 2,3,etc) and another slow(smaller increment value).

- **Time Complexity:** Each pointer goes through an element at max once, so the time complexity would be `O(n)`.


### Sliding Window
**Idea:** Maintain a window `[left, right]` over a subarray or substring. Each time when you slide that window over full array, you can update the computed state based on the removed and added element in that window instead of computing it from scratch.

- **Two Types**
    - **Fixed Size:** The size of the window always stays the same to some constant k.
    - **Variable Size:** Here when we slide the window we always increment the right index, otherwise it won't be a valid sliding window. The left index will increment by `0 to right-1` based on the condition of the problem. e.g. longes subarray problems would try to keep the lowest left index, the shortest sub array will keep the highest left index value.

- Keep in mind that subarray sum problems need the array elements non negative otherwise shrinking the left index won't gurentee the reduction of the sum of the sum array.
- **Time Complexity:** Each element enters or leaves the window exactly once, so the time complexity would be `O(n)`.


### Prefix Sums
**Idea:** Here idea is to precompute the sum for each index. e.g. `prefix[i] = nums[0]+...+nums[i-1]` then the sum of any window `[l,r]` would be `nums[l]+...+nums[r] = prefix[r+1] - prefix[l]`