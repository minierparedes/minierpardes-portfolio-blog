---
title: LeetCode 217 Contains duplicate
excerpt: 'Given an array of integers, find if the array contains any duplicates.'
date: '2020-12-23'
thumb_image: images/natalia-y-NScCnMEYHQ0-unsplash.jpg
thumb_image_alt: duplicates copies of p
image: images/cool-mahogany.jpg
image_alt: duplicates copies of p
seo:
  title: The Elements of Great Workplace Design
  description: >-
    Vis accumsan feugiat adipiscing nisl amet adipiscing accumsan blandit
    accumsan sapien blandit
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: The Elements of Great Workplace Design
      keyName: property
    - name: 'og:description'
      value: >-
        Vis accumsan feugiat adipiscing nisl amet adipiscing accumsan blandit
        accumsan sapien blandit
      keyName: property
    - name: 'og:image'
      value: images/11.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: The Elements of Great Workplace Design
    - name: 'twitter:description'
      value: >-
        Vis accumsan feugiat adipiscing nisl amet adipiscing accumsan blandit
        accumsan sapien blandit
    - name: 'twitter:image'
      value: images/11.jpg
      relativeUrl: true
template: post
subtitle: 'Pattern: Frequency counter'
---
# Coding challenge

Given an array of integers, find if the array contains any duplicates.
Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

### examples:

```javascript
Input: [1,2,3,1]
Output: true

Input: [1,2,3,4]
Output: false

Input: [1,1,1,3,3,4,3,2,4,2]
Output: true
```

<br>

## Breakdown and Discussion of challenge

The challenge is asking for the function to be able to find **ANY** duplicate values. Whenever the input is an array and it requires to **find** matching values my immediate thought to help me find a solution is to use an object. The object can be use to map out all the given inputs from the array to the object and check against the given array's values to see if the values have been assigned already and there is a match.

## Approach

Create an empty object and a for loop. Inside the for loop set an `if`  statement where we ask: is the value in the array inside the object? if so `return true` . Followed by taking each of the values from  the array and mapping them to the object's keys, setting each of the object's values to true. Lastly the function `return false` if no match is found.

#### time complexity

Mapping out array values to the object will take the same amount of operations as the number of input increases making this _**O(n)**_.

#### space complexity

There is use of only one object ``` match ``` to store the key/value pairs from the given array ``` nums ``` .<br> Key maps to each array value and each of the key's value is set to true, giving it a space complexity of _***O(n)***_.

## Code

```javascript
function containsDuplicate(nums) {
    const match = {};
    for (let i = 0; i < nums.length; i++) {
        if (nums[i] in match) return true;
        
        match[nums[i]] = true;
    }
    return false;
};
```

<br>
<br>

## Road to 170

**LC: 1**

This is the first Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad