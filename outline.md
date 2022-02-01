Best Time to Buy And Sell Stock (from leetcode https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

Prompt: You are given an array prices where prices[i] is the price of a given stock on the ith day.
You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

Example: 
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.

Solution Code: 
```
var maxProfit = function(prices) {
    let max = 0;
    let smallest = Infinity;
    
    for(let i = 0; i < prices.length; i++) {
        let curPrice = prices[i];
        smallest = Math.min(smallest, curPrice)
        max = Math.max(prices[i] - smallest, max)
        }
    }
    return max
};
```

Solution Explained: 

We need to track our max profit as we move through the array. Initialize a variable 'max' to 0, that we can update throughout the array as we calculate new profits.

We also want to know where our smallest price is - this is a strong contender for where we want to buy. Initialize this as variable 'smallest' set to Infinity. We will update this also as we move through the array, comparing the current price at 'i' to our smallest price. 

To calculate the profit at each station 'i', subtract the smallest seen price, smallest, from the current price, prices[i]. If the current profit level is larger than any we've seen before, set max equal to the current profit level. 

After our for loop is complete, we should have the correct max value. return it. 

Video explanation: https://www.youtube.com/watch?v=mj7N8pLCJ6w
