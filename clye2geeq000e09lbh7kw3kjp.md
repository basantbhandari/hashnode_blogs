---
title: "78. Subsets"
datePublished: Tue Jul 09 2024 07:04:56 GMT+0000 (Coordinated Universal Time)
cuid: clye2geeq000e09lbh7kw3kjp
slug: 78-subsets
tags: dsa

---

Given an integer array `nums` of **unique** elements, return *all possible*

*subsets*

*(the power set)*.

The solution set **must not** contain duplicate subsets. Return the solution in **any order**.

**Example 1:**

```python
Input: nums = [1,2,3]
Output: [[],[1],[2],[1,2],[3],[1,3],[2,3],[1,2,3]]
```

**Example 2:**

```python
Input: nums = [0]
Output: [[],[0]]
```

**Constraints:**

* `1 <= nums.length <= 10`
    
* `-10 <= nums[i] <= 10`
    
* All the numbers of `nums` are **unique**.
    

Solution:

```python
class Solution:
    def subsets(self, nums: List[int]) -> List[List[int]]:
        res = []

        subset = []

        def dfs(i):
            if i >= len(nums):
                res.append(subset.copy())
                return
            subset.append(nums[i])
            dfs(i + 1)
            subset.pop()
            dfs(i + 1)

        dfs(0)
        return res
```