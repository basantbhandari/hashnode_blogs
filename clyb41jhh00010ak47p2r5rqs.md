---
title: "739. Daily Temperatures"
datePublished: Sun Jul 07 2024 05:26:03 GMT+0000 (Coordinated Universal Time)
cuid: clyb41jhh00010ak47p2r5rqs
slug: 739-daily-temperatures
tags: dsa

---

Given an array of integers `temperatures` represents the daily temperatures, return *an array* `answer` *such that* `answer[i]` *is the number of days you have to wait after the* `i<sup>th</sup>` *day to get a warmer temperature*. If there is no future day for which this is possible, keep `answer[i] == 0` instead.

**Example 1:**

```python
Input: temperatures = [73,74,75,71,69,72,76,73]
Output: [1,1,4,2,1,1,0,0]
```

**Example 2:**

```python
Input: temperatures = [30,40,50,60]
Output: [1,1,1,0]
```

**Example 3:**

```python
Input: temperatures = [30,60,90]
Output: [1,1,0]
```

**Constraints:**

* `1 <= temperatures.length <= 10<sup>5</sup>`
    
* `30 <= temperatures[i] <= 100`
    

Solution:

```python
class Solution:
    def dailyTemperatures(self, temperatures: List[int]) -> List[int]:
        res = [0] * len(temperatures)
        stack = []  # pair: (temp, index)

        for i, t in enumerate(temperatures):
            while stack and t > stack[-1][0]:
                stackT, stackInd = stack.pop()
                res[stackInd] = i - stackInd
            stack.append((t, i))
        return res
```