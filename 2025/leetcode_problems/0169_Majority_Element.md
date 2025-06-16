# 169. Majority Element
Given an array nums of size n, return the majority element.

The majority element is the element that appears more than ⌊n / 2⌋ times. You may assume that the majority element always exists in the array.

Example 1:
```shell
Input: nums = [3,2,3]
Output: 3
```

Example 2:
```shell
Input: nums = [2,2,1,1,1,2,2]
Output: 2
```

Constraints:
```shell
n == nums.length
1 <= n <= 5 * 104
-109 <= nums[i] <= 109
```

Follow-up: Could you solve the problem in linear time and in O(1) space?

## Pseudocode-1(Linear time & space)
- for each element in nums:
    - if element already in the map:
        - increment the corresponding count.
        - set max count and max count element if this count is greater than current count.
    - else
        - set the count as 1 for that element.
        - if max count is 0 then set this element as max count element.
- return the max count element.


## Solution-1(Linear time & space)
```golang
func majorityElement(nums []int) int {
	valMap := make(map[int]int)
    maxC := 0
	maxVal := 0
    /* 
    note: here we could have first constructed a map and then used 
    another for loop to check for the maximum count. But doing that
    in the same for loop saves significant amount of time.
    */
	for _, v := range nums {
		if val, ok := valMap[v]; ok {
			valMap[v] = val + 1
            if val + 1 > maxC{
                maxVal = v
                maxC = val+1
            }
		} else {
			valMap[v] = 1
            if maxC == 0{
                maxVal = v
                maxC = 1
            }
		}
	}
	return maxVal
}
```


## Pseudocode-2(Linear time & constant space)
Moore's Voting Algorithm or  Boyer-Moore Majority Vote Algorithm
- majorityElement = random value
- majorityCount = 0
- for each element in the list:
    - if majorityCount is 0 then set current element as majorityElement and set majorityCount = 1.
    - else
        - if current element == majority element then increment majorityCount
        - else decrement majorityCount
- return majorityElement



## Solution-2(Linear time & constant space)
```golang
func majorityElement(nums []int) int {
	majorityElement := -1
	majorityCount := 0
	v := 0
	for _, v = range nums {
		if majorityCount == 0 {
			majorityElement = v
			majorityCount = 1
		} else {
			if v == majorityElement {
				majorityCount++
			} else {
				majorityCount--
			}
		}
	}
	return majorityElement
}
```