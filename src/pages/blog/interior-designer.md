---
title: How To Choose An Interior Designer
subtitle: >-
  Dynamic Programming
excerpt: >-
  Id massa aliquet arcu accumsan lorem amet accumsan commodo odio cubilia ac eu
  interdum placerat placerat arcu commodo lobortis adipiscing semper ornare
  pellentesque.
date: '2017-03-26'
thumb_image: images/fabian-fauth-RiWvn39cZSQ-unsplash.jpg
thumb_image_alt: endless staircase
seo:
  title: How To Choose An Interior Designer
  description: >-
    Id massa aliquet arcu accumsan lorem amet accumsan commodo odio cubilia ac
    eu interdum placerat
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: How To Choose An Interior Designer
      keyName: property
    - name: 'og:description'
      value: >-
        Id massa aliquet arcu accumsan lorem amet accumsan commodo odio cubilia
        ac eu interdum placerat
      keyName: property
    - name: 'og:image'
      value: images/10.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: How To Choose An Interior Designer
    - name: 'twitter:description'
      value: >-
        Id massa aliquet arcu accumsan lorem amet accumsan commodo odio cubilia
        ac eu interdum placerat
    - name: 'twitter:image'
      value: images/10.jpg
      relativeUrl: true
template: post
image: images/friendly-pine.jpg
image_alt: endless staircase
---

## Coding challenge

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

##### Constraints


`1 <= n <= 45
`

#### examples:


```javascript
Example 1:

Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps

Example 2:

Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
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
function climbStairs(nums) {
    if (nums === 1) return 1;

    let first = 1;
    let second = 2;
    for (let i = 3; i <= nums; i++) {
        let third = first + second;
        first = second;
        second = third;
    }
    return second;
};
```

<br>
<br>

## Road to 170

**LC: 5**

This is the fifth Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad