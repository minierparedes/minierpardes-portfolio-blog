---
title: LeetCode 53 Maximum subarray
subtitle: dynamic programming
excerpt: >-
  Given an integer array nums, find the contiguous subarray (containing at least
  one number) which has the largest sum and return its sum.
date: '2021-01-04'
thumb_image: images/antonio-garcia-ndz_u1_tFZo-unsplash.jpg
thumb_image_alt: an array of solar panels
image: images/5.jpg
image_alt: an array of solar panels
seo:
  title: LeetCode 53 Maximum subarray
  description: >-
    Given an integer array nums, find the contiguous subarray (containing at
    least one number) which has the largest sum and return its sum.
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: LeetCode 53 Maximum subarray
      keyName: property
    - name: 'og:description'
      value: >-
        Given an integer array nums, find the contiguous subarray (containing at
        least one number) which has the largest sum and return its sum.
      keyName: property
    - name: 'og:image'
      value: images/5.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: LeetCode 53 Maximum subarray
    - name: 'twitter:description'
      value: >-
        Given an integer array nums, find the contiguous subarray (containing at
        least one number) which has the largest sum and return its sum.
    - name: 'twitter:image'
      value: images/5.jpg
      relativeUrl: true
template: post
---

## Coding challenge

Given an integer array nums, find the contiguous subarray (containing at least one number) which has the largest sum and return its sum.

Follow up: If you have figured out the O(n) solution, try coding another solution using the divide and conquer approach, which is more subtle.

##### Constraints


`1 <= nums.length <= 2 * 104
-231 <= nums[i] <= 231 - 1
`

#### examples:


```javascript
Example 1:

Input: nums = [-2,1,-3,4,-1,2,1,-5,4]
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
Example 2:

Input: nums = [1]
Output: 1

Example 3:

Input: nums = [0]
Output: 0

Example 4:

Input: nums = [-1]
Output: -1

Example 5:

Input: nums = [-2147483647]
Output: -2147483647
```
<br>

## Breakdown and Discussion of challenge

This challenge is about finding out how many combinations can there be within the given input using a one step or two steps. This challenge requires a more creative thinking for a solution, something that can be either a calculation or an interesting programmatic approach.

The pattern for this problem is Dynamic Programming, and the method for solving the challenge is a variable swap within a for loop.


## Approach

In the function the first step is for an if statement to check if the given input is equal to 1, if so then `return` `1`, as there is only  one combination for that 1. Next, create and initialize two variables, `first` to `1` and `second` to `2` . 

Now we will iterate with a for loop, setting the initializer variable to start at `i = 3` and the condition for the for loop to iterate is the variable `i` is `<=` the input `nums`. Within the loop we create and initialize a third variable to adding both `first` and `second`, `third = first + second`. Next, within the loop we will perform a variable swap:

`first = second` <br>
`second = third`

Lastly, the function returns `second`.


#### time complexity

 _**O(n)**_.

#### space complexity

_***O(1)***_.

## Code

```javascript
function maxSubArray(nums) {
    let current_sum = 0;
    let max_sum = -Infinity;
    for(let i = 0; i < nums.length; i++){
        current_sum = Math.max(nums[i], current_sum + nums[i])
        max_sum = Math.max(max_sum, current_sum);
    }
    return max_sum;
};
```

<br>
<br>

## Road to 170

**LC: 7**

This is the fifth Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad