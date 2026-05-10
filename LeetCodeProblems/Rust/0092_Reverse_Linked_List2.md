# 92. Reverse Linked List II
Given the head of a singly linked list and two integers left and right where left <= right, reverse the nodes of the list from position left to position right, and return the reversed list.

### Example 1:
```shell
Input: head = [1,2,3,4,5], left = 2, right = 4
Output: [1,4,3,2,5]
```

### Example 2:
```shell
Input: head = [5], left = 1, right = 1
Output: [5]
```

### Constraints:
```shell
The number of nodes in the list is n.
1 <= n <= 500
-500 <= Node.val <= 500
1 <= left <= right <= n
```

Follow up: Could you do it in one pass?


## Solution

### Pseudocode
```rs
```

### Rust
```rs
// Definition for singly-linked list.
// #[derive(PartialEq, Eq, Clone, Debug)]
// pub struct ListNode {
//   pub val: i32,
//   pub next: Option<Box<ListNode>>
// }
// 
// impl ListNode {
//   #[inline]
//   fn new(val: i32) -> Self {
//     ListNode {
//       next: None,
//       val
//     }
//   }
// }
impl Solution {
    pub fn reverse_between(head: Option<Box<ListNode>>, left_val: i32, right_val: i32) -> Option<Box<ListNode>> {
        // at least one element will be there in a list.
        let mut first = head.clone();
        let mut current = head;
        let mut previous: Option<Box<ListNode>> = None;
        let mut next: Option<Box<ListNode>> = None;
        let mut left: Option<Box<ListNode>> = None;
        loop {
            // there is a possibility of never finding left element
            let Some(cur) = current.clone() else{break;};
            if cur.val == left_val {
                next = cur.next;
                left = current.clone();
                break;
            }
            previous = current;
            current = cur.next;
        }
        loop {
            // there can be just a single element in the list.
            let Some(mut nex) = next.clone() else{break;};

            let temp = nex.next;
            // reversing operation.
            nex.next = current;
            // at the end current will contain the right element.
            current = next;
            next = temp;

            if nex.val == right_val {
                break;
            }
        }

        // if there is some element before left element, then set its next as right element
        if let Some(mut pre) = previous{
            pre.next = current;
        }else{
            // if there are no element to the left, then right element is the first
            first = current;
        }

        // left will be found for sure
        if let Some(mut lef) = left {
            lef.next = next;
        }
        

        return first;
    }
}
```