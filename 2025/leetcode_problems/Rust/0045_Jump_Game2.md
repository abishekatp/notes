# 45. Jump Game II
You are given a 0-indexed array of integers nums of length n. You are initially positioned at nums[0].

Each element nums[i] represents the maximum length of a forward jump from index i. In other words, if you are at nums[i], you can jump to any nums[i + j] where:
```
0 <= j <= nums[i] and
i + j < n
```
Return the minimum number of jumps to reach nums[n - 1]. The test cases are generated such that you can reach nums[n - 1].

### Example 1:
```shell
Input: nums = [2,3,1,1,4]
Output: 2
Explanation: The minimum number of jumps to reach the last index is 2. Jump 1 step from index 0 to 1, then 3 steps to the last index.
```

### Example 2:
```shell
Input: nums = [2,3,0,1,4]
Output: 2
```

### Constraints:
```shell
1 <= nums.length <= 10^4
0 <= nums[i] <= 1000
It's guaranteed that you can reach nums[n - 1].
```


## Solution 1
- Here the core problem is that we need to figure out minimum number of steps needed to reach the position greater than or equal to the last position.
- We can always choose the best available option as greedy approach, that will make us jump more than minimum number of jumps needed.
- Here the key is that we need to find the next best suitable position to jump.

### Pseudocode
```rs
- jump(nums):
    - len = len(nums)
    - if len <= 1 return 0
    - jumps = 0
    - while i < len or (i + avial_jums != len -1)
        - find the next best available j to jump from the i
            - decrement the current available jumps
            - if j found
                - available jumps = nums[j]
                - i = j
        - if next best available jumps found
            - jumps++
    - return jumps
```


### Rust
```rs
impl Solution {
    pub fn jump(nums: Vec<i32>) -> i32 {
        let le: i32 = nums.len().try_into().unwrap();
        // in this case 0 jumps needed
        if le <= 1 {
            return 0;
        }

        let mut jumps = 0;
        let mut i = -1;
        while i < le {
            i += 1;
            let mut avail_jumps = *nums.get(i as usize).unwrap();
            if avail_jumps >= le - i - 1 {
                return jumps + 1;
            }

            let mut is_jumped = false;
            // find the next big available jump
            let start = i + 1;
            let end = i + avail_jumps + 1;

            for j in (start..end) {
                avail_jumps -= 1;
                let val = *nums.get(j as usize).unwrap();
                if val > avail_jumps {
                    // assign i to the next jumped position.
                    // set to one index less to accommodate auto increment at the beginning.
                    i = j - 1;
                    avail_jumps = val;
                    is_jumped = true;
                }
            }
            // increment jumps only if we had jumped.
            if is_jumped {
                jumps += 1;
            }
        }
        return jumps;
    }
}
```

- Time complexity: $O(n^2)$. 
    - But I think this should take time around $O(n)$ or $O(n log(n))$ something like that. Because the inner loop will jump to the next best position by skipping in between indeces.
- Space complexity: $O(1)$