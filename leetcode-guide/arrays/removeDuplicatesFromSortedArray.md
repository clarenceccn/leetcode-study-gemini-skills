# Remove Duplicates from Sorted Array

## What the problem is asking
Remove duplicates from a sorted array in-place so that each unique element appears only once. Return the number of unique elements $k$. The first $k$ elements of the array must hold these unique values.

## Constraints
*   1 <= nums.length <= 3 * 10^4
*   -100 <= nums[i] <= 100
*   `nums` is sorted in non-decreasing order.

## Examples
*   **Input:** nums = [1,1,2] -> **Output:** 2, nums = [1,2,_]
*   **Input:** nums = [0,0,1,1,1,2,2,3,3,4] -> **Output:** 5, nums = [0,1,2,3,4,_,_,_,_,_]

## Essence
Use two pointers: one to scan the array (`p1`) and one to track where to write the next unique element (`writeIdx`). Since it's sorted, duplicates are always adjacent.

## Solutions & Complexity
*   **Primary Approach: Two Pointers (Write & Scan)**
    *   Initialize `writeIdx` at 1.
    *   Iterate through the array starting from index 1.
    *   If the current element is different from the previous one, it's unique; write it at `writeIdx` and increment `writeIdx`.
    *   **Time:** O(N) - Single pass through the array.
    *   **Space:** O(1) - Modified in-place.
*   **Alternative Approach: Pythonic Slicing (Not truly in-place $O(1)$ space)**
    *   Use `set()` to find unique elements, sort them, and assign back to a slice `nums[:]`.
    *   **Time:** O(N log N) due to sorting.
    *   **Space:** O(N) to store the set/list.

## Code
### Provided Solution
```python
from typing import List

class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        # approach 1: turn nums into a set then list and sort loop over nums and copy and return size of set 
        # approach 2: two pointers, in place set and return size

        if len(nums) == 1:
            return 1

        lastWritten = nums[0]
        writeIdx = 1
        p1 = 1

        while True:
            while p1 < len(nums) and nums[p1] == lastWritten:
                p1 += 1
            if p1 < len(nums):
                lastWritten = nums[p1]
                nums[writeIdx] = lastWritten
                writeIdx += 1
            else:
                break
        return writeIdx
```

### Alternative: Standard Two-Pointer
```python
from typing import List

class Solution:
    def removeDuplicates(self, nums: List[int]) -> int:
        if not nums:
            return 0
        
        # write_ptr tracks the position for the next unique element
        write_ptr = 1
        
        # Scan through the array starting from the second element
        for i in range(1, len(nums)):
            # If current element is different from the last unique one
            if nums[i] != nums[i - 1]:
                nums[write_ptr] = nums[i]
                write_ptr += 1
                
        return write_ptr
```
