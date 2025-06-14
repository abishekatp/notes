# Array / String

## 26. Remove Duplicates from Sorted Array

Given an integer array nums sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same. Then return the number of unique elements in nums.

Consider the number of unique elements of nums to be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the unique elements in the order they were present in nums initially. The remaining elements of nums are not important as well as the size of nums.
Return k.

### Solution
```go
func removeDuplicates(nums []int) int {
	uniqueMap := make(map[int]bool)
	k := 0
	for i := 0; i < len(nums); {
		if _, ok := uniqueMap[nums[i]]; !ok {
			uniqueMap[nums[i]] = true
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

### Explanation









## 27. Remove Element

Given an integer array nums and an integer val, remove all occurrences of val in nums in-place. The order of the elements may be changed. Then return the number of elements in nums which are not equal to val.

Consider the number of elements in nums which are not equal to val be k, to get accepted, you need to do the following things:

Change the array nums such that the first k elements of nums contain the elements which are not equal to val. The remaining elements of nums are not important as well as the size of nums.
Return k.

### Solution
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

### Explanation






## 80. Remove Duplicates from Sorted Array II

Given an integer array nums sorted in non-decreasing order, remove some duplicates in-place such that each unique element appears at most twice. The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array nums. More formally, if there are k elements after removing the duplicates, then the first k elements of nums should hold the final result. It does not matter what you leave beyond the first k elements.

Return k after placing the final result in the first k slots of nums.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

### Solution
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

### Explanation

- This one is straightforward. We will copy the elment that is not equal to the `val` at the beginning of the array. If the current element is equal to `val`, then we will just increment `i` and does not increment `k`(since we haven't copied any new valid element to the current position of the `k`). This process continues untill `i = len(nums) -1` which is last index of the array `nums`.







## 88. Merge Sorted Array
You are given two integer arrays nums1 and nums2, sorted in non-decreasing order, and two integers m and n, representing the number of elements in nums1 and nums2 respectively.

Merge nums1 and nums2 into a single array sorted in non-decreasing order.

The final sorted array should not be returned by the function, but instead be stored inside the array nums1. To accommodate this, nums1 has a length of m + n, where the first m elements denote the elements that should be merged, and the last n elements are set to 0 and should be ignored. nums2 has a length of n.

### Solution
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

### Explanation
- Here they have given two arrays. Both of them are sorted in increasing order. We have to merge them in such a way that the resulting array also will be in sorted order.
- I am using a third array to copy one element at a time either from array `nums1` or `nums2`. We have two variables `i` and `j` to keep track of already visited indeces in respective arrays.
- We compare the current element from array `nums1` with the current element in Array `nums2`. Whichever is less we copy that to the `final` array, then increase the respective index. 
- If either one of the array index exceeds the corresponding array length, then we will exit from this loop. 
- Then append all the remaining elements from the other array to the `final` array. This logic works because both `nums1` and `nums2` are sorted in increasing order and we have moved all the elements from one of them already.

### Space efficient solution
- Since the `nums1` has the extra space to store all the elements from both `nums1` and `nums2`. We could have started from the last element of `nums1` and `nums2`. Checked whichever is bigger, then copied the bigger element at the end of the `nums1`. This way we could have achieved the same result without using the extra space(`final` array).








