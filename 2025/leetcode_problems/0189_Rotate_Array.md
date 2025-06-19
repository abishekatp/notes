# 189. Rotate Array
Given an integer array nums, rotate the array to the right by k steps, where k is non-negative.

Example 1:
```shell
Input: nums = [1,2,3,4,5,6,7], k = 3
Output: [5,6,7,1,2,3,4]
Explanation:
rotate 1 steps to the right: [7,1,2,3,4,5,6]
rotate 2 steps to the right: [6,7,1,2,3,4,5]
rotate 3 steps to the right: [5,6,7,1,2,3,4]
```

Example 2:
```shell
Input: nums = [-1,-100,3,99], k = 2
Output: [3,99,-1,-100]
Explanation: 
rotate 1 steps to the right: [99,-1,-100,3]
rotate 2 steps to the right: [3,99,-1,-100]
```

Constraints:
```shell
1 <= nums.length <= 105
-231 <= nums[i] <= 231 - 1
0 <= k <= 105
 ```

Follow up:

Try to come up with as many solutions as you can. There are at least three different ways to solve this problem.
Could you do it in-place with O(1) extra space?

## Pseudocode 1
- moduloK:= finding moduloK to avoid unnecessary rotations.
- visitedMap:= to keep track already rotated element in first moduloK positions(if first moduloK elements are rotated correctely, other elements will be rotated automatically since we are continuously rotating until we reach the index that we started with)
- for each element in the first moduloK positions:
	- if not already rotated due to the rotation of previous elements start the rotaion:
		- while j does not reach the already visited index:
			- shift(rotate) element at i'th postion to moduloK positions. 
			- then shift(rotate) the element at i+modulK for moduloK psitions.
			- continue until condition breaks.


## Solution 1 (linear time and space O(moduloK))

```golang
func rotate(nums []int, k int) {
	length := len(nums)
	moduloK := k % length
    visitedMap := make(map[int]bool)
  
	for i:=0;i<moduloK;i++{
        if _,ok:=visitedMap[i];!ok{
            visitedMap[i] = true
            preEle := nums[i]
	        // when all the elements are shifted the last element will be moved at the  
            // place where the first element has been moved out.
	        for j := i + moduloK; ; j = (j + moduloK) % length {
		        temp := nums[j]
		        nums[j] = preEle
		        preEle = temp
                if _, ok:=visitedMap[j];ok{
                    break
                }else if j < moduloK{
                    visitedMap[j] = true
                }
	        }
        }
    }
}
```

- Time complexity: each element will be shifted at most one time so time complexity is O(n)
- Space complexity: only space that is used extra is the map to show already visited elements(less than moduloK): moduloK = O(n) where n = len(nums)