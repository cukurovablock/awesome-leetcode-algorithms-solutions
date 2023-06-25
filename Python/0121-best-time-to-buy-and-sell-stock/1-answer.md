# [✅ Two Pointer to solve the 🧑🏻‍💻 Best Time to Buy and Sell Stock Problem on 🐍 Python language](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/solutions/3681310/two-pointer-to-solve-the-best-time-to-buy-and-sell-stock-problem-on-python-language/)

## 🧑🏻‍💻 Approach

This problem is a classic example of the Two Pointer Technique where two pointers are maintained to find the maximum difference (maximum profit in this case). The pointers are `left` and `right`, where `left` is initially at the start of the array, and `right` is the second element. We move the right pointer to the end of the array and for each move, we check if the current profit (`prices[right] - prices[left]`) is greater than the current maxProfit. If it is, we update maxProfit. If `prices[right]` is less than `prices[left]`, it means that we could buy at a lower price at `right`, so we update `left` to `right`.

## 🔐 Code

``` python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        left, right = 0, 1
        maxProfit = 0

        while right < len(prices):
            if prices[left] < prices[right]:
                profit = prices[right] - prices[left]
                maxProfit = max(maxProfit, profit)
            else:
                left = right
            right += 1
        
        return maxProfit
```

## 🧩 Complexity

- Time complexity:
The time complexity of this approach is $O(n)$ where n is the length of the prices array. This is because we are running a loop to traverse through the prices array once.

- Space complexity:
The space complexity is $O(1)$ as we are only using a constant amount of space to store our variables (left, right, maxProfit, and profit).
