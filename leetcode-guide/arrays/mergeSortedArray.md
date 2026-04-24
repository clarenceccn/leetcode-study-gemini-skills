# Merge Sorted Array

## What the problem is asking
Merge two sorted arrays `nums1` and `nums2` into `nums1` in-place. `nums1` has extra space at the end to accommodate `nums2`.

## Constraints
*   `nums1.length == m + n`
*   `nums2.length == n`
*   0 <= m, n <= 200
*   Arrays are sorted in non-decreasing order.

## Examples
*   **Input:** nums1 = [1,2,3,0,0,0], m = 3, nums2 = [2,5,6], n = 3 -> **Output:** [1,2,2,3,5,6]
*   **Input:** nums1 = [1], m = 1, nums2 = [], n = 0 -> **Output:** [1]

## Essence
Fill `nums1` from the **back to the front** to avoid overwriting elements that haven't been compared yet.

## Solutions & Complexity
*   **Primary Approach: Three Pointers (Back-to-Front)**
    *   Compare elements from the end of `nums1` (at index `m-1`) and `nums2` (at index `n-1`).
    *   Place the larger element at the very end of `nums1` (at index `m+n-1`).
    *   **Time:** O(m + n) - Each element is visited once.
    *   **Space:** O(1) - Sorting is done in-place.
*   **Alternative Approach: Merge and Sort**
    *   Replace the trailing zeros in `nums1` with elements from `nums2` and then call `nums1.sort()`.
    *   **Time:** O((m + n) log(m + n)) - Due to the sorting algorithm.
    *   **Space:** O(1) or O(m + n) depending on the sort implementation.

## Code
### Provided Solution
```python
from typing import List

class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        """
        Do not return anything, modify nums1 in-place instead.
        """
        # approach 1: modify nums1 in place by addings nums2 to the end and sort the whole array
        # approach 2: three pointers, one to write spot, one to nums1 last elem and one to nums2 last elem

        writeIdx = m + n - 1
        first = m - 1
        second = n - 1

        while writeIdx >= 0 and (first >= 0 or second >= 0):
            if second < 0 or (first >= 0 and nums1[first] >= nums2[second]):
                nums1[writeIdx] = nums1[first]
                first -= 1
            else:
                nums1[writeIdx] = nums2[second]
                second -= 1
            writeIdx -= 1
```

### Alternative: Idiomatic Three-Pointer
```python
from typing import List

class Solution:
    def merge(self, nums1: List[int], m: int, nums2: List[int], n: int) -> None:
        # Pointers for nums1, nums2, and the write position
        p1, p2, p = m - 1, n - 1, m + n - 1
        
        # While there are elements to compare in both arrays
        while p1 >= 0 and p2 >= 0:
            if nums1[p1] > nums2[p2]:
                nums1[p] = nums1[p1]
                p1 -= 1
            else:
                nums1[p] = nums2[p2]
                p2 -= 1
            p -= 1
        
        # If nums2 still has elements, copy them (nums1 elements are already in place)
        # Using slicing for idiomatic bulk copy
        if p2 >= 0:
            nums1[:p2 + 1] = nums2[:p2 + 1]
```
