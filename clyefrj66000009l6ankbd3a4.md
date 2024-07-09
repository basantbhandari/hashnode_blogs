---
title: "90. Subsets II"
datePublished: Tue Jul 09 2024 13:17:30 GMT+0000 (Coordinated Universal Time)
cuid: clyefrj66000009l6ankbd3a4
slug: 90-subsets-ii
tags: dsa

---

Given an integer array `nums` that may contain duplicates, return *all possible*

*subsets*

*(the power set)*.

The solution set **must not** contain duplicate subsets. Return the solution in **any order**.

**Example 1:**

```python
Input: nums = [1,2,2]
Output: [[],[1],[1,2],[1,2,2],[2],[2,2]]
```

**Example 2:**

```python
Input: nums = [0]
Output: [[],[0]]
```

**Constraints:**

* `1 <= nums.length <= 10`
    
* `-10 <= nums[i] <= 10`
    

Solution:

```python
class Solution:
    def subsetsWithDup(self, nums: List[int]) -> List[List[int]]:
        res = []
        nums.sort()

        def backtrack(i, subset):
            # base case
            if i == len(nums):
                res.append(subset[::])
                return

            # all subset that include nums[i]
            subset.append(nums[i])
            backtrack(i + 1, subset)

            # all subset that does not include nums[i]
            subset.pop()
            # skip the duplicate
            while i + 1 < len(nums) and nums[i] == nums[i + 1]:
                i += 1
            backtrack(i + 1, subset)

        backtrack(0, [])
        return res
```