# Palindrome Number

## What the problem is asking
Determine if an integer is a palindrome (reads the same forwards and backwards) without necessarily converting it to a string.

## Constraints
*   -2^31 <= x <= 2^31 - 1
*   Negative numbers are not palindromes.

## Examples
*   **Input:** x = 121 -> **Output:** true
*   **Input:** x = -121 -> **Output:** false
*   **Input:** x = 10 -> **Output:** false

## Essence
Check if the sequence of digits in a number is symmetric.

## Solutions & Complexity
*   **Primary Approach: Digit Array + Two Pointers**
    *   Extract digits into a list using modulo and floor division.
    *   Use two pointers to compare digits from both ends.
    *   **Time:** O(log N) - Number of digits in x.
    *   **Space:** O(log N) - To store the digits.
*   **Alternative Approach: Reversing Half the Number**
    *   Reverse the second half of the number and compare it with the first half.
    *   Avoids overflow and uses no extra space.
    *   **Time:** O(log N)
    *   **Space:** O(1)
*   **Alternative Approach: String Conversion**
    *   Convert to string and check if `s == s[::-1]`.
    *   **Time:** O(log N)
    *   **Space:** O(log N)

## Code
```python
class Solution:
    def isPalindrome(self, x: int) -> bool:
        # approach 1: convert int to string O(n), O(d)
        # approach 2: two pointers, convert int to a digit array  O(n), O(d)
        if x < 0:
            return False
        digits = Solution.convertToDigitArray(x)

        start = 0
        end = len(digits) - 1
        while start <= end:
            if digits[start] != digits[end]:
                return False
            start += 1
            end -= 1
        return True

    @staticmethod
    def convertToDigitArray(x: int) -> List[int]:
        res = []
        if x == 0: return [0]
        while x > 0:
            digit = x % 10
            res.append(digit)
            x //= 10
        return res
```

```python
class Solution:
	def isPalindrome(self, x: int) -> bool:
		return str(x)[::-1] == str(x)
		
```
