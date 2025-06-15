# 125. Valid Palindrome

A phrase is a palindrome if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string s, return true if it is a palindrome, or false otherwise.


Example 1:

```shell
Input: s = "A man, a plan, a canal: Panama"
Output: true
Explanation: "amanaplanacanalpanama" is a palindrome.
```

Example 2:
```shell
Input: s = "race a car"
Output: false
Explanation: "raceacar" is not a palindrome.
```

Example 3:

```shell
Input: s = " "
Output: true
Explanation: s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.
```

Constraints:
```shell
1 <= s.length <= 2 * 105
s consists only of printable ASCII characters.
```


## Pseudocode

- 



## Solution

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
