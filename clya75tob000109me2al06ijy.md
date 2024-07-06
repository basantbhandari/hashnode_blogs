---
title: "Product of Array Except Self"
datePublished: Sat Jul 06 2024 14:05:36 GMT+0000 (Coordinated Universal Time)
cuid: clya75tob000109me2al06ijy
slug: product-of-array-except-self
tags: dsa

---

Given an integer array `nums`, return *an array* `answer` *such that* `answer[i]` *is equal to the product of all the elements of* `nums` *except* `nums[i]`.

The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.

You must write an algorithm that runs in `O(n)` time and without using the division operation.

**Example 1:**

```python
Input: nums = [1,2,3,4]
Output: [24,12,8,6]
```

**Example 2:**

```python
Input: nums = [-1,1,0,-3,3]
Output: [0,0,9,0,0]
```

**Constraints:**

* `2 <= nums.length <= 10<sup>5</sup>`
    
* `-30 <= nums[i] <= 30`
    
* The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.
    

Solution:

```python
class Solution:
    def productExceptSelf(self, nums: List[int]) -> List[int]:
        res = [1] * (len(nums))

        for i in range(1, len(nums)):
            res[i] = res[i-1] * nums[i-1]


        postfix = 1
        for i in range(len(nums) - 1, -1, -1):
            res[i] *= postfix
            postfix *= nums[i]
            
        return res
```