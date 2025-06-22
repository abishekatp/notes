# 27. Remove Element
Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums.
Return k.
Custom Judge:

The judge will test your solution with the following code:

```shell
int[] nums = [...]; // Input array
int val = ...; // Value to remove
int[] expectedNums = [...]; // The expected answer with correct length.
                            // It is sorted with no values equaling val.

int k = removeElement(nums, val); // Calls your implementation

assert k == expectedNums.length;
sort(nums, 0, k); // Sort the first k elements of nums
for (int i = 0; i < actualLength; i++) {
    assert nums[i] == expectedNums[i];
}
If all assertions pass, then your solution will be accepted.
```
 

### Example 1:
```shell
Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

### Example 2:
```shell
Input: nums = [0,1,2,2,3,0,4,2], val = 2
Output: 5, nums = [0,1,4,0,3,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums containing 0, 0, 1, 3, and 4.
Note that the five elements can be returned in any order.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

### Constraints:
```shell
0 <= nums.length <= 100
0 <= nums[i] <= 50
0 <= val <= 100
```


## Solution

### Pseudocode
- k:=0
- for i from 0 to n:
    - if num[i]= val:
        - i++
    - else:
        - nums[k] = nums[i]
        - k++ and i++



```go
func removeElement(nums []int, val int) int {
    // all the elements at or before k are already validated to be not to be val.
    k:=0
    for i:=0; i< len(nums);{
        if nums[i] != val{
            // copy the nums[i] to nums[k] if nums[i] is not equal to val.
            nums[k] = nums[i]
            // go to next element
            i++
            // increament k to store the next valid element.
            k++
        }else{
            // if nums[i] is equal to val then ignore that element and go to next element.
            i++
        }
    }
    return k
}
```

```
Time complexity: O(n)
Space complexity: O(1)
```
