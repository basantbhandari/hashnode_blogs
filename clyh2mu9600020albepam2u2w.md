---
title: "70. Climbing Stairs"
datePublished: Thu Jul 11 2024 09:33:15 GMT+0000 (Coordinated Universal Time)
cuid: clyh2mu9600020albepam2u2w
slug: 70-climbing-stairs
tags: dsa

---

You are climbing a staircase. It takes `n` steps to reach the top.

Each time you can either climb `1` or `2` steps. In how many distinct ways can you climb to the top?

**Example 1:**

```python
Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```

**Example 2:**

```python
Input: n = 3
Output: 3
Explanation: There are three ways to climb to the top.
1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step
```

**Constraints:**

* `1 <= n <= 45`
    

Solution:

```python
class Solution:
    def climbStairs(self, n: int) -> int:
        # DP, base case
        one, two = 1,1
        for i in range(n-1):
            temp = one
            one = one + two
            two = temp

        return one
```