# 88. Merge Sorted Array
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.

### Example 1:
```shell
Input: nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3
Output: [1,2,2,3,5,6]
Explanation: The arrays we are merging are [1,2,3] and [2,5,6].
The result of the merge is [1,2,2,3,5,6] with the underlined elements coming from nums1.
```

### Example 2:
```shell
Input: nums1 = [1], m = 1, nums2 = [], n = 0
Output: [1]
Explanation: The arrays we are merging are [1] and [].
The result of the merge is [1].
```

### Example 3:
```shell
Input: nums1 = [0], m = 0, nums2 = [1], n = 1
Output: [1]
Explanation: The arrays we are merging are [] and [1].
The result of the merge is [1].
Note that because m = 0, there are no elements in nums1. The 0 is only there to ensure the merge result can fit in nums1.
```

### Constraints:
```shell
nums1.length == m + n
nums2.length == n
0 <= m, n <= 200
1 <= m + n <= 200
-10^9 <= nums1[i], nums2[j] <= 10^9
 ```

Follow up: Can you come up with an algorithm that runs in O(m + n) time?

## Solution

### Pseudocode
```go
- 
```

### Golang
```go
func merge(nums1 []int, m int, nums2 []int, n int)  {
    i := 0
    j := 0
    final := []int{}
    // copy the minimum element from the current index of either nums1 or nums2
    // this for loop ends when at least one of the array is fully copied.
    for i<m && j < n {
        if nums1[i] < nums2[j]{
            final = append(final, nums1[i])
            i++
        }else {
            final = append(final, nums2[j])
            j++
        }
    }

    // move any remaining elements from nums1 to final array.
    for i < m {
        final = append(final, nums1[i])
        i++
    }
    // move any remaining elements from nums2 to final array.
    for j < n {
        final = append(final, nums2[j])
        j++
    }

    // note: check the space efficient solution.
    // copy the result to the nums1
    for k:=0; k < m+n; k++{
        nums1[k] = final[k]
    }
}
```

```
Time Complexity: O(m+n)
Space Complexity: O(m+n)
```

### Explanation
- Here they have given two arrays. Both of them are sorted in increasing order. We have to merge them in such a way that the resulting array also will be in sorted order.
- I am using a third array to copy one element at a time either from array `nums1` or `nums2`. We have two variables `i` and `j` to keep track of already visited indeces in respective arrays.
- We compare the current element from array `nums1` with the current element in Array `nums2`. Whichever is less we copy that to the `final` array, then increase the respective index. 
- If either one of the array index exceeds the corresponding array length, then we will exit from this loop. 
- Then append all the remaining elements from the other array to the `final` array. This logic works because both `nums1` and `nums2` are sorted in increasing order and we have moved all the elements from one of them already.

### Space efficient solution
- Since the `nums1` has the extra space to store all the elements from both `nums1` and `nums2`. We could have started from the last element of `nums1` and `nums2`. Checked whichever is bigger, then copied the bigger element at the end of the `nums1`. This way we could have achieved the same result without using the extra space(`final` array).



