---
title: LeetCode 121 Best time to buy and sell stock
excerpt: >-
 Say you have an array for which the ith element is the price of a given stock on day i.
If you were only permitted to complete at most one transaction (i.e., buy one and sell one 
share of the stock), design an algorithm to find the maximum profit.
date: '2020-12-31'
thumb_image: images/8_thumb.jpg
thumb_image_alt: bullish market statue
image: images/8.jpg
image_alt: bullish market statue
seo:
  title: LeetCode 121 Best time to buy and sell stock
  description: >-
    Dynamic Programming
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: LeetCode 121 Best time to buy and sell stock
      keyName: property
    - name: 'og:description'
      value: >-
        Dynamic Programming
      keyName: property
    - name: 'og:image'
      value: images/8.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: LeetCode 121 Best time to buy and sell stock
    - name: 'twitter:description'
      value: >-
        Dynamic Programming
    - name: 'twitter:image'
      value: images/8.jpg
      relativeUrl: true
template: post
---

## Coding challenge

Say you have an array for which the ith element is the price of a given stock on day i.

If you were only permitted to complete at most one transaction (i.e., buy one and sell one 
share of the stock), design an algorithm to find the maximum profit.

Note that you cannot sell a stock before you buy one.

#### examples:


```javascript
Input: [7,1,5,3,6,4]
Output: 5
Explanation: 
Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5. 
Not 7-1 = 6, as selling price needs to be larger than buying price.

Input: [7,6,4,3,1]
Output: 0
Explanation: In this case, no transaction is done, i.e. max profit = 0.

```
<br>

## Breakdown and Discussion of challenge

The point of the challenge is to be able find the minimum value within the array in order to buy, followed by being able to find the maximum value within the array after you buy, in order to sell. 
<br>The function needs to be able to return the maximum profit you can get from any given array input.


## Approach

In a function we need to be able to keep track of both the minimum and the maximum values. Within the function two variables will be declared and initialized, `maxPrice = 0` and `minPrice = Number.MAX_VALUE`, the latter is initialized to Number.MAX_VALUE in order to ensure that its value is always less than the maximum possible number on each turn. Useful as an initial value when searching for the minimum value.

The for loop will iterate through every index of the array `prices` asking the following question with an if statement: `if (prices[i] < minPrice)` set `prices[i]` to be the `minPrice`, otherwise set `maxPrice` to be maximum return value from `Math.max(maxPricem prices[i] - minPrice)`. All that is left is for the function to `return maxPrice`

#### time complexity

 _**O(n)**_.

#### space complexity

_***O(1)***_.

## Code

```javascript
function maxProfit(prices) {
    let maxPrice = 0;
    let minPrice = Number.MAX_VALUE;

    for (let i = 0; i < prices.length; i++) {
        if (prices[i] < minPrice) {
            minPrice = prices[i];
        }else {
            maxPrice = Math.max(maxPrice, prices[i]- minPrice);
        }
    }
    return maxPrice;
};
```

<br>
<br>

## Road to 170

**LC: 6**

This is the 6th Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad