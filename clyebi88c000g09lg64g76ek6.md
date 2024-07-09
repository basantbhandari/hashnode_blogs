---
title: "39. Combination Sum"
datePublished: Tue Jul 09 2024 11:18:18 GMT+0000 (Coordinated Universal Time)
cuid: clyebi88c000g09lg64g76ek6
slug: 39-combination-sum
tags: dsa

---

Given an array of **distinct** integers `candidates` and a target integer `target`, return *a list of all* ***unique combinations*** *of* `candidates` *where the chosen numbers sum to* `target`*.* You may return the combinations in **any order**.

The **same** number may be chosen from `candidates` an **unlimited number of times**. Two combinations are unique if the

frequency

of at least one of the chosen numbers is different.

The test cases are generated such that the number of unique combinations that sum up to `target` is less than `150` combinations for the given input.

**Example 1:**

```python
Input: candidates = [2,3,6,7], target = 7
Output: [[2,2,3],[7]]
Explanation:
2 and 3 are candidates, and 2 + 2 + 3 = 7. Note that 2 can be used multiple times.
7 is a candidate, and 7 = 7.
These are the only two combinations.
```

**Example 2:**

```python
Input: candidates = [2,3,5], target = 8
Output: [[2,2,2,2],[2,3,3],[3,5]]
```

**Example 3:**

```python
Input: candidates = [2], target = 1
Output: []
```

**Constraints:**

* `1 <= candidates.length <= 30`
    
* `2 <= candidates[i] <= 40`
    
* All elements of `candidates` are **distinct**.
    
* `1 <= target <= 40`
    

Solution:

```python
class Solution:
    def combinationSum(self, nums: List[int], target: int) -> List[List[int]]:
        res = []

        def dfs(i, cur, total):
            # base case with result, we found the desired result
            if total == target:
                res.append(cur.copy())
                return
            # base case
            if i >= len(nums) or total > target:
                return

            cur.append(nums[i])
            dfs(i, cur, total + nums[i])
            
            cur.pop()
            dfs(i + 1, cur, total)

        dfs(0, [], 0)
        return res
```