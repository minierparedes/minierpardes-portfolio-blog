---
title: LeetCode 268 Missing Number
excerpt: >-
Given an array nums containing n distinct numbers in the range `[0, n]`, return the only number 
in the range that is missing from the array.
date: '2020-12-24'
thumb_image: images/makers-on-a-map.jpg
image: images/marvelous-goat.jpg
seo:
  title: LeetCode 268 Missing Number
  description: Frequency Counter
  extra:
    - name: 'og:type'
      value: article
      keyName: property
    - name: 'og:title'
      value: LeetCode 268 Missing Number
      keyName: property
    - name: 'og:description'
      value: Frequency Counter
      keyName: property
    - name: 'og:image'
      value: images/9.jpg
      keyName: property
      relativeUrl: true
    - name: 'twitter:card'
      value: summary_large_image
    - name: 'twitter:title'
      value: LeetCode 268 Missing Number
    - name: 'twitter:description'
      value: Frequency Counter
    - name: 'twitter:image'
      value: images/9.jpg
      relativeUrl: true
template: post
thumb_image_alt: missing number markers on a map
image_alt: missing number markers on a map
---

## Coding challenge

Given an array nums containing n distinct numbers in the range `[0, n]`, return the only number 
in the range that is missing from the array. 

##### Constraints


`n == nums.length
 1 <= n <= 104
 0 <= nums[i] <= n
 All the numbers of nums are unique.
`

#### examples:


```javascript
Input: nums = [3,0,1]
Output: 2
Explanation: n = 3 since there are 3 numbers, so all numbers are in
the range [0,3]. 2 is the missing number 
in the range since it does not appear in nums.

---------

Input: nums = [0,1]
Output: 2
Explanation: n = 2 since there are 2 numbers, so all numbers are in
the range [0,2]. 2 is the missing number 
in the range since it does not appear in nums.

---------

Input: nums = [9,6,4,2,3,5,7,0,1]
Output: 8
Explanation: n = 9 since there are 9 numbers, so all numbers are in
the range [0,9]. 8 is the missing number 
in the range since it does not appear in nums.

---------

Input: nums = [0]
Output: 1
Explanation: n = 1 since there is 1 number, so all numbers are in
the range [0,1]. 1 is the missing number 
in the range since it does not appear in nums.

```
<br>

## Breakdown and Discussion of challenge

Given an unsorted array of integer values, we need to **check** all the numbers and see which number is the **missing** from the given range. For challenges that require **finding** something within the array, against some factor, in this case being the array's range of numbers, I like to immediately think of using an object to map the array's values to the object. This method allows for the object to have all the values and then I can check against the array to see what is missing, compare, check for duplicates ect..  


## Approach

Within the function we create an object `missingNum` and an array `result`. Use a for loop to iterate through the array mapping each array's index to the object keys and setting each key's value to false. Create a second loop to set to true each object key's that is in the object using the array's values. A last for loop is create, this time a for in loop, grabbing each key from the object and using an `if` statement asking: `missingNum[key] === false` take the `result` array and push the `key` with false value to it. Now the function will `return result[0]` the fist element in the array.

#### time complexity

 _**O(n)**_.

#### space complexity

_***O(n)***_.

## Code

```javascript
function missingNumber(nums) {
    const missingNum = {};
    const result = [];

    for (let i = 0; i <= nums.length; i++) {
        missingNum[i] = false;
    }
    for (let i = 0; i < nums.length; i++) {
        missingNum[nums[i]] = true;
    }
    for (const key in missingNum) {
        if (missingNum[key] === false) result.push(key)
    }


    return result[0];
};
```

<br>
<br>

## Road to 170

**LC: 2**

This is the second Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad