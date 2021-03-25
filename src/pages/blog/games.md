---
title: LeetCode 136 Single Number
excerpt: Frequency Counter
date: '2020-12-28'
thumb_image: images/andreas-wagner-FtuaKc0on6Y-unsplash.jpg
thumb_image_alt: 'a single mushroom, single number'
image: images/adorable-cabbage.jpg
image_alt: 'a single mushroom, single number'
seo:
  title: What are some of the best designed video games
  description: Diam sit amet nisl suscipit adipiscing bibendum est ultricies integer
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: What are some of the best designed video games
      keyName: property
    - name: 'og:description'
      value: Diam sit amet nisl suscipit adipiscing bibendum est ultricies integer
      keyName: property
    - name: 'og:image'
      value: images/6.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: What are some of the best designed video games
    - name: 'twitter:description'
      value: Diam sit amet nisl suscipit adipiscing bibendum est ultricies integer
    - name: 'twitter:image'
      value: images/6.jpg
      relativeUrl: true
template: post
---

## Coding challenge

Given a non-empty array of integers nums, every element appears twice except for one. Find that single one.

Follow up: Could you implement a solution with a linear runtime complexity and without using extra memory? 

##### Constraints


`1 <= nums.length <= 3 * 104
 -3 * 104 <= nums[i] <= 3 * 104
 0 <= nums[i] <= n
 Each element in the array appears 
 twice except for one element which appears only once.
`

#### examples:


```javascript
Input: nums = [2,2,1]
Output: 1

Input: nums = [4,1,2,1,2]
Output: 4

Input: nums = [1]
Output: 1

```
<br>

## Breakdown and Discussion of challenge

Given an unsorted array of integer values, all having a duplicate, we need to **check** all the numbers and see which number is the **single**, **unique**, number that only appears once. Whenever there is a challenge that requires **finding** something within the array, against some factor, in this case getting a single unique number from all the ones with their duplicates, I like to immediately think of using an object to map the array's values to the object. I wanted to try implementing a two pointer approach, but I was not successful in getting the pattern to work with numbers in the middle or near the end of the array, e.g. `[2, 1, 2, 4, 1]`. I believe that given enough time, or help, I will be able to get to the solution. 

Using an object, allowing it to have all the array values as keys and I then check the object to see which of its key values have a higher value than 1, returning that unique key.


## Approach

Create an object `uniq` within the function to map all the array values to a key, setting each value to 1. Use a for loop to iterate through all the array values. In the for loop we use an if statement to ask: if the object `uniq` when called using the array's values `uniq[nums[i]]` as its key property, is available then increment++ its value by one, otherwise set its value to one. A second loop is set, this time a for in loop, to check if object `uniq` has any key property whos value is stricly equals to 1? if so then return the key's value else return -1.

#### time complexity

 _**O(n)**_.

#### space complexity

_***O(n)***_.

## Code

```javascript
function singleValue(nums) {
    const uniq = {};

    for (let i = 0; i < nums.length; i++) {
        uniq[nums[i]] ? uniq[nums[i]]++ : uniq[nums[i]] = 1;
    }
    for ( let i in uniq) {
        if (uniq[i] === 1) return i;
    }
    return -1;
};
```

<br>
<br>

## Road to 170

**LC: 4**

This is the fourth Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad