---
title: "46. Permutations"
datePublished: Tue Jul 09 2024 12:18:03 GMT+0000 (Coordinated Universal Time)
cuid: clyedn2xh000309l86doc12nw
slug: 46-permutations
tags: dsa

---

Given an array `nums` of distinct integers, return *all the possible permutations*. You can return the answer in **any order**.

**Example 1:**

```python
Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
```

**Example 2:**

```python
Input: nums = [0,1]
Output: [[0,1],[1,0]]
```

**Example 3:**

```python
Input: nums = [1]
Output: [[1]]
```

**Constraints:**

* `1 <= nums.length <= 6`
    
* `-10 <= nums[i] <= 10`
    
* All the integers of `nums` are **unique**.
    

Solution:

```python
class Solution:
    def permute(self, nums: List[int]) -> List[List[int]]:
        if len(nums) == 0:
            return [[]]
        res = []
        permutations = self.permute(nums[1:])
        print(permutations)
        for p in permutations:
            for i in range(len(p)+ 1):
                p_copy = p.copy()
                p_copy.insert(i, nums[0])
                res.append(p_copy)
        return res
```