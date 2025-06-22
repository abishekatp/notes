# 209. Minimum Size Subarray Sum
Given an array of positive integers nums and a positive integer target, return the minimal length of a subarray whose sum is greater than or equal to target. If there is no such subarray, return 0 instead.

### Example 1:
```shell
Input: target = 7, nums = [2,3,1,2,4,3]
Output: 2
Explanation: The subarray [4,3] has the minimal length under the problem constraint.
```

### Example 2:
```shell
Input: target = 4, nums = [1,4,4]
Output: 1
Example 3:

Input: target = 11, nums = [1,1,1,1,1,1,1,1]
Output: 0
 ```

### Constraints:
```shell
1 <= target <= 109
1 <= nums.length <= 105
1 <= nums[i] <= 104
```

Follow up: If you have figured out the O(n) solution, try coding another solution of which the time complexity is O(n log(n)).


### Some Questions

- Does sub array elements should be adjacent elements of the original array? Yes that is what sub array means. If you want non-adjacent elements, that’s called a subsequence, not a subarray. A subarray is a contiguous non-empty sequence of elements within an array.


## Solution
***Time Complexity:***
- Even though we have two nested for loops. Inner for loop will only run when sum is greater than or equal to target. If you think about it at most it will iterate the whole array of nums one time. Only in the worst case when last element is equal to the target value, the inner for loop will iterate the whole nums array, otherwise it won't ever iterate the whole array just once.

``` 
time complexity(~): O(n)
where n = len(nums)
```

***Space Complexity:***

- We are only using constant number varialble year. So the space complexity is constant.

``` 
space complexity(~): O(1)
```

### Pseudocode

- sum := 0
- finalMinLen := len(nums) + 1
- i := 0
- for each index `j` in nums:
    - sum = sum + nums[j]
    - if sum >= target:
        - finalMinLen = j - i + 1
    - while sum - nums[i] >= target:
        - discard the starting elements from the sub array by incrementing index i.
        - if j - i + 1 < finalMinLen:
            - finalMinLen = j - i + 1
- if finalMinLen > len(nums): only when target is never achieved
    - return 0
- else return finalMinLen


`Solution: If you want it in one line then here it is: Add at the tail and discard at the front`


```go
func minSubArrayLen(target int, nums []int) int {
	sum := 0 // current sub array sum
	finalMinLen := len(nums) + 1
	i := 0
	for j := 0; j < len(nums); j++ {
		// add the current element to the sub array sum
		sum = sum + nums[j]
		if sum >= target {
			minLen := j - i + 1
			if minLen < finalMinLen {
				finalMinLen = minLen
			}
		}

		// while current sum is greater than or equal to target discard the initial elements.
		for sum-nums[i] >= target {
			sum = sum - nums[i]
			i = i + 1
			minLen := j - i + 1
			if minLen < finalMinLen {
				finalMinLen = minLen
			}
		}
	}

	if finalMinLen > len(nums) {
		return 0
	}
	return finalMinLen
}
```