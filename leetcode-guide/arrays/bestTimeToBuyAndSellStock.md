# Best Time to Buy and Sell Stock

## What the problem is asking
Find the maximum profit you can make by buying a stock on one day and selling it on a future day. You only get one transaction.

## Constraints
*   1 <= prices.length <= 10^5
*   0 <= prices[i] <= 10^4

## Examples
*   **Input:** [7,1,5,3,6,4] -> **Output:** 5 (Buy at 1, sell at 6)
*   **Input:** [7,6,4,3,1] -> **Output:** 0 (No profit possible)

## Essence
Track the lowest price seen so far (`minSeen`) and calculate the potential profit at each step.

## Solutions & Complexity
*   **Primary Approach: One Pass (Greedy)**
    *   Iterate through the prices once.
    *   Maintain `minSeen` to track the lowest price encountered so far.
    *   Calculate `profit = current_price - minSeen` and update `maxProfit` if this profit is higher.
    *   **Time:** O(N) - Single pass through the prices.
    *   **Space:** O(1) - Only two variables used.
*   **Alternative Approach: Brute Force**
    *   Use nested loops to check every possible buy/sell pair.
    *   **Time:** O(N^2) - Will TLE (Time Limit Exceeded) for $10^5$ elements.
    *   **Space:** O(1)

## Code
### Provided Solution
```python
from typing import List

class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # approach 1: use extra space and one pass by record the min value at i-1 and calc max at each i
        # approach 2: brute force 2 for loops
        # approach 3: no extra space and one pass using 2 variables to track min seen

        if not prices:
            return 0
        if len(prices) == 1:
            return 0
        
        minSeen = prices[0]
        maxProfit = 0

        for i in range(1, len(prices)):
            maxProfit = max(maxProfit, prices[i] - minSeen)
            minSeen = min(minSeen, prices[i])
        
        return maxProfit
```

### Alternative: Clean One-Pass
```python
from typing import List

class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        # float('inf') is a useful way to initialize a minimum tracker
        min_price = float('inf')
        max_profit = 0
        
        for price in prices:
            if price < min_price:
                min_price = price
            elif price - min_price > max_profit:
                max_profit = price - min_price
                
        return max_profit
```
