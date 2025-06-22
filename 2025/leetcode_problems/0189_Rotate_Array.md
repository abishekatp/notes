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


## Solution 1: (linear time and space O(moduloK))

- Each element will be shifted at most one time so time complexity is O(n)
- Only space that is used extra is the map to show already visited elements(less than moduloK): moduloK = O(n) where n = len(nums)

```
Time complexity: O(n)
Space complexity: O(n)
```

###  Pseudocode
- moduloK := k % len(nums)
- visitedMap := new map()
- for each element in the first moduloK positions:
	- if i not in the visitedMap:
		- j := moduloK
		- while j not in the visitedMap:
		    - j = (j + moduloK) % len(nums)
			- shift(rotate) element at i'th postion to moduloK positions. 
			- then shift(rotate) the element at i+modulK for moduloK psitions.



```golang
func rotate(nums []int, k int) {
	length := len(nums)
	moduloK := k % length // finding moduloK to avoid unnecessary rotations.
    visitedMap := make(map[int]bool)//to keep track already rotated element in first moduloK positions(if first moduloK elements are rotated correctely, other elements will be rotated automatically since we are continuously rotating until we reach the index that we started with)
  
	for i:=0;i<moduloK;i++{
		// visitedMap contains already visited indces < moduloK
        if _,ok:=visitedMap[i];!ok{
            visitedMap[i] = true
            preEle := nums[i]
	        // when we increment and find moduloK at some point it will always reach a index which has already been visited
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

## Solution 2: (O(n) time and space)
```
Time complexity: O(n)
Space complexity: O(n)
```


### Pseudocode
This should have been my obvious solution. Anyway we are going to use `O(n)` space and time. We could create another temp array to store all the roated elements.

- temp := [] 
- for i from 0 to n-1:
	- temp[(i + moduloK) % len(nums)] = temp[i]
- for i from 0 to n-1:
	- nums[i] = temp[i]


```golang
func rotate(nums []int, k int) {
	length := len(nums)
	temp := make([]int, length)
	moduloK := k % length

	for i := 0; i < length; i++ {
		temp[(i + moduloK) % length] = nums[i]
	}
	for i := 0; i < length; i++ {
		nums[i] = temp[i]
	}
}
```

## Solution 3: O(n) time and O(1) space
- we are reversing elements in place so the space complexity is reduced here.
```
Time complexity: O(n)
Space complexity: O(1)
```

### Pseudocode
- moduloK := k % len(nums)
- center := floor(len(nums) / 2)
- for i from 0 to center-1: reverse logic
	- temp := nums[i]
	- end := len(nums) - 1 -i
	- nums[i] = nums[end]
	- nums[end] = temp
- apply the same reverse logic for first k elements and next len(nums) - k elements individually


```golang
func rotate(nums []int, k int) {
	length := len(nums)
	moduloK := k % length
    // revers all elements
    reverse(nums, 0, length-1)
    // reverse first k elements
    reverse(nums, 0, moduloK - 1)
    // reverese elements from k to n
    reverse(nums,  moduloK, length - 1)
}

func reverse(nums []int, startInd int, endInd int){
    center := endInd - startInd + 1
    if center % 2 == 0{
        center = startInd + (center / 2)
    }else{
        center = startInd + ((center - 1) / 2)
    }

    j := 0 
    for i:=startInd; i < center; i++{
        end := endInd - j // j equalent to. i - startInd
        temp := nums[i]
        nums[i] = nums[end]
        nums[end] = temp
        j++
    }
}
```

```
nums = [1,2,3,4,5,6,7] and k = 3

whole revers
[7,6,5,4,3,2,1]

first k elements reverse
[5,6,7,4,3,2,1]

remaining n-k elements reverse
[5,6,7,1,2,3,4]
```