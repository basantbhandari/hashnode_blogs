---
title: "121. Best Time to Buy and Sell Stock"
datePublished: Sun Jul 07 2024 13:31:30 GMT+0000 (Coordinated Universal Time)
cuid: clybldtgw000109js1o7r8msu
slug: 121-best-time-to-buy-and-sell-stock
tags: dsa

---

You are given an array `prices` where `prices[i]` is the price of a given stock on the `i<sup>th</sup>` day.

You want to maximize your profit by choosing a **single day** to buy one stock and choosing a **different day in the future** to sell that stock.

Return *the maximum profit you can achieve from this transaction*. If you cannot achieve any profit, return `0`.

**Example 1:**

```python
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```

**Example 2:**

```python
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
```

**Constraints:**

* `1 <= prices.length <= 10<sup>5</sup>`
    
* `0 <= prices[i] <= 10<sup>4</sup>`
    

Solution:

```python
class Solution:
    def maxProfit(self, prices: List[int]) -> int:
        l, r = 0, 1 # left=buy, right=sell
        maxP = 0

        while r < len(prices):
            if prices[l] < prices[r]:
                profit = prices[r] - prices[l]
                maxP = max(maxP, profit)
            else:
                l = r
            r += 1
        
        return maxP
```