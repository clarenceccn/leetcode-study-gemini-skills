# Two Sum

## What the problem is asking
Find the indices of two numbers in an array that add up to a specific target.

## Constraints
*   2 <= nums.length <= 10^4
*   -10^9 <= nums[i] <= 10^9
*   -10^9 <= target <= 10^9
*   Only one valid answer exists.
*   You cannot use the same element twice.

## Examples
*   **Input:** nums = [2,7,11,15], target = 9 -> **Output:** [0,1]
*   **Input:** nums = [3,2,4], target = 6 -> **Output:** [1,2]
*   **Input:** nums = [3,3], target = 6 -> **Output:** [0,1]

## Essence
Find a pair of numbers $(a, b)$ such that $a + b = target$ using indices.

## Solutions & Complexity
*   **Primary Approach: One-Pass Hash Map**
    *   Iterate through the array while storing seen numbers and their indices in a hash map.
    *   For each number, check if its complement (`target - num`) already exists in the map.
    *   **Time:** O(N)
    *   **Space:** O(N)
*   **Alternative Approach: Brute Force**
    *   Check every possible pair using nested loops.
    *   **Time:** O(N^2)
    *   **Space:** O(1)
*   **Alternative Approach: Two Pointers (with Sorting)**
    *   Sort the array and use two pointers (left and right) to find the sum.
    *   Note: Requires original indices to be preserved before sorting.
    *   **Time:** O(N log N)
    *   **Space:** O(N)

## Code
```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        # use a dictionary where f(x) = a, x is the target - nums[i], a = i in nums[i]
        # loop through list
        # search dict[target-nums[b]] exists, where b is current idx. if it does then return [a, b]
        # approach 1: brute force o(n^2), O(1)
        # approach 2: binary search + sort O(nlogn), O(n)
        # approach 3: one pass dictionary store seen O(n), O(n) 
        seen = {}
        for idx, num in enumerate(nums):
            desired = target - num
            if desired in seen:
                return [seen[desired], idx]
            else:
                seen[num] = idx
```
