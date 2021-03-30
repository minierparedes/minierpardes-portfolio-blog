---
title: LeetCode 303 Range Sum Query - Immutable
subtitle: Dynamic Programming
date: '2021-01-07'
thumb_image_alt: train yard
image_alt: train yard
excerpt: >-
  Given an integer array nums, find the sum of the elements between indices i
  and j (i ≤ j), inclusive.  Implement the NumArray class:   NumArray(int[]
  nums) Initializes the object with the integer array nums.  int sumRange(int i,
  int j) Return the sum of the elements of the nums array in the range [i, j]
  inclusive (i.e., sum(nums[i], nums[i + 1], ... , nums[j])).
seo:
  title: LeetCode 303 Range Sum Query - Immutable
  description: Dynamic Programming
  robots: []
  extra: []
  type: stackbit_page_meta
template: post
thumb_image: images/max-vertsanov-qvRuue12Huw-unsplash.jpg
image: images/mighty-lime.jpg
---
##### Constraints


`0 <= nums.length <= 104
-105 <= nums[i] <= 105
0 <= i <= j < nums.length
At most 104 calls will be made to sumRange.
`

#### examples:


```javascript
Example 1:

Input
["NumArray", "sumRange", "sumRange", "sumRange"]
[[[-2, 0, 3, -5, 2, -1]], [0, 2], [2, 5], [0, 5]]
Output
[null, 1, -1, -3]

Explanation
NumArray numArray = new NumArray([-2, 0, 3, -5, 2, -1]);
numArray.sumRange(0, 2); // return 1 ((-2) + 0 + 3)
numArray.sumRange(2, 5); // return -1 (3 + (-5) + 2 + (-1)) 
numArray.sumRange(0, 5); // return -3 ((-2) + 0 + 3 + (-5) + 2 + (-1))
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
function NumArray(nums) {
    this.total_sum = [0];

    for (let i = 0; i < nums.length; i++) {
        this.total_sum[i + 1] = nums[i] + this.total_sum[i];
    }
};

const numArrayCopy = new NumArray([-2, 0, 3, -5, 2, -1]);

NumArray.prototype.sumRange = function(i, j) {
    return this.total_sum[j + 1] - this.total_sum[i]
};
```

<br>
<br>

## Road to 170

**LC: 8**

This is the 8th Leetcode challenge of the 170 challenges from the [LeetCode Patterns](https://seanprashad.com/leetcode-patterns/) by Sean Prashad