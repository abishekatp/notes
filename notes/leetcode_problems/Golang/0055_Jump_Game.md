# 55. Jump Game
You are given an integer array nums. You are initially positioned at the array's first index, and each element in the array represents your maximum jump length at that position.

Return true if you can reach the last index, or false otherwise.

### Example 1:
```shell
Input: nums = [2,3,1,1,4]
Output: true
Explanation: Jump 1 step from index 0 to 1, then 3 steps to the last index.
```

### Example 2:
```shell
Input: nums = [3,2,1,0,4]
Output: false
Explanation: You will always arrive at index 3 no matter what. Its maximum jump length is 0, which makes it impossible to reach the last index.
``` 

### Constraints:
```shell
1 <= nums.length <= 10^4
0 <= nums[i] <= 10^5
```


## Solution
This solution is simple. Each index tells us the maximum number of steps available.
Using it we can move to the next index. If the value at that index is greater than the
currently avialable jumps, then we would choose that value as available jumps.

### Pseudocode
```go
- availJump := 0
- le := len(nums)
- for i from 0 to le-1:
    - if jumps at index i > availJump:
        - availJump = nums[i]
    - if availJump is enough to reach last index:
        - return true
    - else if no jumps available:
        - return false
    - jump to next index
- return false
```

### Golang
```go
func canJump(nums []int) bool {
    availJump:=0
    le := len(nums)
    for i:=0; i<le; i++{
        // using a greedy approach always choosing the max number of steps that is available.
        if nums[i] > availJump{
            availJump = nums[i]
        }

        // having this condition first will pass even the case [0]
        if availJump >= le - 1 - i{
            return true
        }else if availJump <= 0 {
            /* 
            since we are always choosing the max jumps available
            when availJump is 0 that means there is no way of reaching last index.
            */ 
            return false
        }
        availJump--
    }
    return false
}
```