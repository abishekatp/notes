# 80. Remove Duplicates from Sorted Array II
Given an integer array nums sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array nums. More formally, if there are k elements after removing the duplicates, then the first k elements of nums should hold the final result. It does not matter what you leave beyond the first k elements.

Return k after placing the final result in the first k slots of nums.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

Custom Judge:

The judge will test your solution with the following code:

```shell
int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}
If all assertions pass, then your solution will be accepted.
```
 

Example 1:

```shell
Input: nums = [1,1,1,2,2,3]
Output: 5, nums = [1,1,2,2,3,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 1, 1, 2, 2 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

Example 2:

```shell
Input: nums = [0,0,1,1,1,1,2,3,3]
Output: 7, nums = [0,0,1,1,2,3,3,_,_]
Explanation: Your function should return k = 7, with the first seven elements of nums being 0, 0, 1, 1, 2, 3 and 3 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

Constraints:

```shell
1 <= nums.length <= 3 * 104
-104 <= nums[i] <= 104
nums is sorted in non-decreasing order.
```

## Pseudocode

- 


## Solution
```go
func removeDuplicates(nums []int) int {
    // elements before the index k are the valid elements
	k := 0
	for i := 0; i < len(nums); {
		count := 1
        // check for at most two duplicated before the index k
		for j := 0; j < k; j++ {
			if nums[j] == nums[i] {
				count++
			}
		}
		if !(count > 2) {
			nums[k] = nums[i]
			k++
			i++
		} else {
			i++
		}
	}
    return k
}
```

## Bonus Section

### Explanation
- This one is straightforward. We will copy the elment that is not equal to the `val` at the beginning of the array. If the current element is equal to `val`, then we will just increment `i` and does not increment `k`(since we haven't copied any new valid element to the current position of the `k`). This process continues untill `i = len(nums) -1` which is last index of the array `nums`.




