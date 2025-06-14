# Two Pointers

## 125. Valid Palindrome
A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.

### Solution

```go
import "unicode"
func isPalindrome(s string) bool {
	i := 0
    f := []rune(strings.ToLower(s))
	j := len(s) - 1
	for j > i {
        r1:= f[i]
        r2:= f[j]
		first := unicode.IsLetter(r1) || unicode.IsDigit(r1)
		second := unicode.IsLetter(r2) || unicode.IsDigit(r2)
		if !(first) {
			i++
		}
		if !(second) {
			j--
		}
		if first && second && r1 == r2 {
			i++
			j--
		} else if first && second {
			return false
		}

	}
	return true
}
```

### Explanation







## 167. Two Sum II - Input Array Is Sorted

Given a 1-indexed array of integers numbers that is already sorted in non-decreasing order, find two numbers such that they add up to a specific target number. Let these two numbers be numbers[index1] and numbers[index2] where 1 <= index1 < index2 <= numbers.length.

Return the indices of the two numbers, index1 and index2, added by one as an integer array [index1, index2] of length 2.

The tests are generated such that there is exactly one solution. You may not use the same element twice.

Your solution must use only constant extra space.

Example 1:

Input: numbers = [2,7,11,15], target = 9
Output: [1,2]
Explanation: The sum of 2 and 7 is 9. Therefore, index1 = 1, index2 = 2. We return [1, 2].


### solution

```go
func twoSum(numbers []int, target int) []int {
    for i:=0; i< len(numbers); i++{
        for j:=0; j<i; j++{
            if numbers[i] + numbers[j] == target{
                return []int{j+1, i+1}
            }
        }
    }
    return []int{-1, -1}
}
```

### Explanation








## 209. Minimum Size Subarray Sum

Given an array of positive integers nums and a positive integer target, return the minimal length of a 
subarray
 whose sum is greater than or equal to target. If there is no such subarray, return 0 instead.


Example 1:

Input: target = 7, nums = [2,3,1,2,4,3]
Output: 2
Explanation: The subarray [4,3] has the minimal length under the problem constraint.

### Solution

```go
func minSubArrayLen(target int, nums []int) int {
	// compute running total
	for i := 1; i < len(nums); i++ {
		nums[i] = nums[i] + nums[i-1]
	}
    
	// compute sub array total using the running total
	return binaryTree(int(math.Round(float64(len(nums)/2))), nums, target)
}

func binaryTree(sub int, nums []int, target int) int {
    if sub >= len(nums){
        return 0
    }

    isTrue := false
    for i := len(nums) - 1; i >= sub; i-- {
        if nums[i]-nums[i-sub] >= target {
            isTrue  = true
        }
    }

    if nums[sub-1] >= target{
        isTrue = true
    }
    if (sub == 1) && isTrue{
        return sub
    }else if sub ==1{
        return 0
    }

    if isTrue{
        lessSub := binaryTree(int(math.Round(float64(sub/2))), nums, target)
        if lessSub!=0{
            return lessSub
        }else{
            return sub
        }
    }
    return binaryTree(sub + int(math.Round(float64(sub/2))), nums, target)
}
```

### Explanation