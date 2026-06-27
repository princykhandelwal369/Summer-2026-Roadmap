# Day 2

## Problem 1 - Best Time to Buy and Sell Stock

### LINK

https://leetcode.com/problems/best-time-to-buy-and-sell-stock/

### DESCRIPTION AND UNDERSTANDING

You are given an array `prices` where `prices[i]` represents the price of a stock on the `i`th day.

You can choose **one day to buy** the stock and **one later day to sell** it. Your goal is to maximize the profit. If no profit can be made, return `0`.

---

The key idea is to keep track of the **lowest stock price seen so far** while iterating through the array.

For each day's price:

* If it is lower than the minimum price seen so far, update the minimum price.

* Otherwise, calculate the profit if the stock were sold today:

  `profit = current_price - minimum_price`

* Compare this profit with the maximum profit found so far and update it if necessary.

Since we only need to scan the array once while remembering the minimum price and maximum profit, a single pass is enough.

### Code

```python
class Solution(object):
    def maxProfit(self, prices):
        minimum = prices[0]
        maxProfit = 0

        for i in range(1, len(prices)):
            if prices[i] < minimum:
                minimum = prices[i]
            else:
                maxProfit = max(maxProfit, prices[i] - minimum)

        return maxProfit
```

### Time Complexity

O(n)

### Space Complexity

O(1)

### What I Learned

* Keeping track of a running minimum while traversing an array.
* Solving an optimization problem in a single pass.
* Updating multiple variables (`minimum` and `maxProfit`) simultaneously.
* Recognizing that storing previous values isn't always necessary—sometimes only the best value so far is enough.
