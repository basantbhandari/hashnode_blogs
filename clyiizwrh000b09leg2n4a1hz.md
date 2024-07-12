---
title: "152. Maximum Product Subarray"
datePublished: Fri Jul 12 2024 09:59:05 GMT+0000 (Coordinated Universal Time)
cuid: clyiizwrh000b09leg2n4a1hz
slug: 152-maximum-product-subarray
tags: dsa

---

Given an integer array `nums`, find a

subarray

that has the largest product, and return*the product*.

The test cases are generated so that the answer will fit in a **32-bit** integer.

**Example 1:**

```python
Input: nums = [2,3,-2,4]
Output: 6
Explanation: [2,3] has the largest product 6.
```

**Example 2:**

```python
Input: nums = [-2,0,-1]
Output: 0
Explanation: The result cannot be 2, because [-2,-1] is not a subarray.
```

**Constraints:**

* `1 <= nums.length <= 2 * 10<sup>4</sup>`
    
* `-10 <= nums[i] <= 10`
    
* The product of any prefix or suffix of `nums` is **guaranteed** to fit in a **32-bit** integer.
    

Solution:

```python
class Solution:
    def maxProduct(self, nums: List[int]) -> int:
        res = nums[0]
        curMin, curMax = 1, 1

        for n in nums:
            tmp = curMax * n
            curMax = max(n * curMax, n * curMin, n)
            curMin = min(tmp, n * curMin, n)
            res = max(res, curMax)
        return res
```