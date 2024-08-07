---
title: "704. Binary Search"
datePublished: Sun Jul 07 2024 07:52:43 GMT+0000 (Coordinated Universal Time)
cuid: clyb9a53p00070alecfob99pd
slug: 704-binary-search
tags: dsa

---

Given an array of integers `nums` which is sorted in ascending order, and an integer `target`, write a function to search `target` in `nums`. If `target` exists, then return its index. Otherwise, return `-1`.

You must write an algorithm with `O(log n)` runtime complexity.

**Example 1:**

```python
Input: nums = [-1,0,3,5,9,12], target = 9
Output: 4
Explanation: 9 exists in nums and its index is 4
```

**Example 2:**

```python
Input: nums = [-1,0,3,5,9,12], target = 2
Output: -1
Explanation: 2 does not exist in nums so return -1
```

**Constraints:**

* `1 <= nums.length <= 10<sup>4</sup>`
    
* `-10<sup>4</sup> < nums[i], target < 10<sup>4</sup>`
    
* All the integers in `nums` are **unique**.
    
* `nums` is sorted in ascending order.
    

Solution:

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l <= r:
            m = l + ((r - l) // 2)  # (l + r) // 2 can lead to overflow
            if nums[m] > target:
                r = m - 1
            elif nums[m] < target:
                l = m + 1
            else:
                return m
        return -1
```