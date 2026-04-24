# Longest Common Prefix

## What the problem is asking
Find the longest string that is a prefix to all strings in a given array.

## Constraints
*   1 <= strs.length <= 200
*   0 <= strs[i].length <= 200
*   All strings consist of lowercase English letters.

## Examples
*   **Input:** ["flower","flow","flight"] -> **Output:** "fl"
*   **Input:** ["dog","racecar","car"] -> **Output:** ""

## Essence
The common prefix is limited by the "most different" strings in the set.

## Solutions & Complexity
*   **Primary Approach: Sorting (Lexicographic comparison)**
    *   Sort the array. The most different strings will be at the first and last positions.
    *   Compare only the first and last strings to find the common prefix.
    *   **Time:** O(N * L log N), where N is the number of strings and L is the average length (sorting strings takes comparison time).
    *   **Space:** O(L) or O(N*L) depending on the sorting implementation's memory usage.
*   **Alternative Approach: Vertical Scanning**
    *   Iterate through characters of the first string and compare them with the same index of all other strings.
    *   Stop at the first mismatch or when a string ends.
    *   **Time:** O(S), where S is the sum of all characters in all strings (Worst case).
    *   **Space:** O(1) (excluding the output string).
*   **Alternative Approach: Pythonic `zip` & `set`**
    *   Use `zip(*strs)` to group characters by index.
    *   Use `set()` on each group; if the set size is 1, the character is common to all.
    *   **Time:** O(S)
    *   **Space:** O(S)

## Code
### Provided Solution
```python
from typing import List

class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        # approach 1: brute force - start with empty "" then loop through each word for matching prefix and stop when current word is not part of it. 
        # approach 2: sort the list of words and compare the first and last word. Due to lexicographic sorting the answer is the the shared prefix amongst the first and last word

        strs.sort()
        return Solution.getLCP(strs[0], strs[-1])

    @staticmethod
    def getLCP(first: str, last: str) -> str:
        for idx, c in enumerate(first):
            if c != last[idx]:
                return first[:idx]
        return first
```

### Alternative: Pythonic Zip
```python
from typing import List

class Solution:
    def longestCommonPrefix(self, strs: List[str]) -> str:
        if not strs:
            return ""
        
        # zip(*strs) pairs characters by index: (s1[0], s2[0], s3[0]), (s1[1], s2[1], s3[1])...
        # We stop as soon as a character set has more than one unique value.
        prefix = []
        for chars in zip(*strs):
            if len(set(chars)) == 1:
                prefix.append(chars[0])
            else:
                break
        
        return "".join(prefix)
```
