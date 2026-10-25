# Week 1 — Question 2: Best Time to Buy and Sell Stock

## Problem

You are given an array `prices` where `prices[i]` is the price of a stock on day `i`.

Choose one day to buy the stock and a later day to sell it. Return the maximum
profit you can achieve. If no profit is possible, return `0`.

You may not sell the stock before buying it.

## Examples

```text
Input:  prices = [7, 1, 5, 3, 6, 4]
Output: 5
Explanation: Buy on day 1 at price 1 and sell on day 4 at price 6.
```

```text
Input:  prices = [7, 6, 4, 3, 1]
Output: 0
Explanation: No profitable transaction is possible.
```

```text
Input:  prices = [2, 4, 1]
Output: 2
Explanation: Buy on day 0 at price 2 and sell on day 1 at price 4.
```

## Constraints

- `2 <= prices.length <= 10^5`
- `0 <= prices[i] <= 10^4`

## Your task

1. Write a brute-force solution first.
2. State its time and space complexity.
3. Improve it to a one-pass solution.
4. Test it with the examples and at least two edge cases.

## Java method signature

```java
public int maxProfit(int[] prices) {
    
    int min = Integer.MAX_VALUE;
    int maxProfit = 0;

    for(int price: prices)
    {
        min = Math.min(min, price);
        maxProfit = Math.max(maxProfit, price - min);
    }

    return maxProfit; 
}
```

## Edge cases to test

- Prices always decrease: `[7, 6, 4, 3, 1]`
- Only two days: `[2, 5]`
- All prices are equal: `[3, 3, 3, 3]`
- The best selling day is near the end: `[5, 4, 3, 2, 10]`

## Hint

Track the lowest buying price seen so far. For each day, calculate the profit
if you sold on that day and keep the maximum profit found.
