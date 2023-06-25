# [✅ Sliding Window to solve the 🧑🏻‍💻 Best Time to Buy and Sell Stock Problem on 🐍 Python language](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/solutions/3681349/sliding-window-to-solve-the-best-time-to-buy-and-sell-stock-problem-on-python-language/)

## 🧑🏻‍💻 Approach

In this problem, we can use a sliding window approach where we iterate over the prices array once, keeping track of the lowest price we've seen so far, and calculate the profit for each price. The approach is to first initialize the lowest price as the first price in the array. Then for each subsequent price, we compare it with the current lowest price. If it's less, we update the lowest price. If it's more, we calculate the profit (current price - lowest price) and compare it with the current maximum profit. If the calculated profit is more, we update the maximum profit. The maximum profit at the end of the iteration is the answer.

## 🔐 Code

``` python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        result = 0
        
        lowest = prices[0]
        for price in prices:
            if price < lowest:
                lowest = price
            result = max(result, price - lowest)
        return result
```

## 🧩 Complexity

- Time complexity: 
The time complexity of this approach is $O(n)$ where n is the length of the prices array. This is because we are running a loop to traverse through the prices array once.

- Space complexity:
The space complexity is $O(1)$ as we are only using a constant amount of space to store our variables (result, lowest, and price).