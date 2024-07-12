---
title: "69. Sqrt(x)"
datePublished: Fri Jul 12 2024 04:45:02 GMT+0000 (Coordinated Universal Time)
cuid: clyi7s1fn00060albeoto5qtg
slug: 69-sqrtx
tags: dsa

---

Given a non-negative integer `x`, return *the square root of* `x` *rounded down to the nearest integer*. The returned integer should be **non-negative** as well.

You **must not use** any built-in exponent function or operator.

* For example, do not use `pow(x, 0.5)` in c++ or `x ** 0.5` in python.
    

**Example 1:**

```python
Input: x = 4
Output: 2
Explanation: The square root of 4 is 2, so we return 2.
```

**Example 2:**

```python
Input: x = 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.
```

**Constraints:**

* `0 <= x <= 2<sup>31</sup> - 1`
    

Solution:

```python
class Solution:
    def mySqrt(self, x: int) -> int:
        l, r = 0, x
        res = 0
        while l <= r:
            m = l + (r-l) // 2
            if m**2 < x:
                l += 1
                res = m
            elif m**2 > x:
                r -= 1
            else:
                return m
            
        return res
```