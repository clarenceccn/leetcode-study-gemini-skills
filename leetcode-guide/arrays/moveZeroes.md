# Move Zeroes

## What the problem is asking
Move all `0`s in an array to the end while maintaining the relative order of the non-zero elements. This must be done in-place.

## Constraints
*   1 <= nums.length <= 10^4
*   -2^31 <= nums[i] <= 2^31 - 1
*   Must modify `nums` in-place.

## Examples
*   **Input:** [0,1,0,3,12] -> **Output:** [1,3,12,0,0]
*   **Input:** [0] -> **Output:** [0]

## Essence
Use a "write" pointer to shift all non-zero elements to the front of the array, then fill the remaining positions with zeros.

## Solutions & Complexity
*   **Primary Approach: Two Pointers (Shift & Fill)**
    *   Iterate through the array with a scan pointer.
    *   Whenever a non-zero element is found, write it to the `writeIdx` and increment `writeIdx`.
    *   After the loop, all non-zero elements are at the front. Fill the rest of the array (from `writeIdx` to the end) with `0`.
    *   **Time:** O(N) - One pass to shift, one partial pass to fill.
    *   **Space:** O(1) - Modified in-place.
*   **Alternative Approach: Two Pointers (Optimal Swap)**
    *   Maintain a `lastNonZero` pointer. When you see a non-zero, swap it with the element at `lastNonZero`.
    *   This minimizes operations by combining the shift and fill into a single pass.
    *   **Time:** O(N)
    *   **Space:** O(1)

## Code
### Provided Solution
```python
from typing import List

class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        """
        Do not return anything, modify nums in-place instead.
        """
        # approach 1: use extra space and do a copy over with 3 loops
        # approach 2: two pointers no extra space, write as I see then do another loop at the end to set zeroes
        writeIdx = 0
        zeroCount = 0
        for i in range(0, len(nums)):
            if nums[i] != 0:
                nums[writeIdx] = nums[i]
                writeIdx += 1
            else:
                zeroCount += 1

        if zeroCount > 0:
            nums[-zeroCount:] = [0] * zeroCount
```

### Alternative: Optimal Swap (One-Pass)
```python
from typing import List

class Solution:
    def moveZeroes(self, nums: List[int]) -> None:
        # last_non_zero tracks where the next non-zero element should go
        last_non_zero = 0
        
        for i in range(len(nums)):
            if nums[i] != 0:
                # Swap elements: the current non-zero moves forward, 
                # and the zero moves back.
                nums[last_non_zero], nums[i] = nums[i], nums[last_non_zero]
                last_non_zero += 1
```
