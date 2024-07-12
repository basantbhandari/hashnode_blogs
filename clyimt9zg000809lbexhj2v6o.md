---
title: "633. Sum of Square Numbers"
datePublished: Fri Jul 12 2024 11:45:54 GMT+0000 (Coordinated Universal Time)
cuid: clyimt9zg000809lbexhj2v6o
slug: 633-sum-of-square-numbers
tags: dsa

---

Given a non-negative integer `c`, decide whether there're two integers `a` and `b` such that `a<sup>2</sup> + b<sup>2</sup> = c`.

**Example 1:**

```python
Input: c = 5
Output: true
Explanation: 1 * 1 + 2 * 2 = 5
```

**Example 2:**

```python
Input: c = 3
Output: false
```

**Constraints:**

* `0 <= c <= 2<sup>31</sup> - 1`
    

Solution:

```python
class Solution:
    def judgeSquareSum(self, c: int) -> bool:
        """
        Two pointer solution
        """
        left, right = 0, int(math.sqrt(c))
        while left <= right:
            if left * left + right * right == c:
                return True
            elif left * left + right * right > c:
                right -= 1
            else:
                left += 1
        return False
```