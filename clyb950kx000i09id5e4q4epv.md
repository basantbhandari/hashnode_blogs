---
title: "84. Largest Rectangle in Histogram"
datePublished: Sun Jul 07 2024 07:48:43 GMT+0000 (Coordinated Universal Time)
cuid: clyb950kx000i09id5e4q4epv
slug: 84-largest-rectangle-in-histogram
tags: dsa

---

Given an array of integers `heights` representing the histogram's bar height where the width of each bar is `1`, return *the area of the largest rectangle in the histogram*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720332632947/4eb3cc90-05f3-40e8-9ad5-dcac1555be4b.jpeg align="center")

```python
Input: heights = [2,1,5,6,2,3]
Output: 10
Explanation: The above is a histogram where width of each bar is 1.
The largest rectangle is shown in the red area, which has an area = 10 units.
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720332657563/2a750f5e-396a-4802-b7ac-1e8381afd00d.jpeg align="center")

```python
Input: heights = [2,4]
Output: 4
```

**Constraints:**

* `1 <= heights.length <= 10<sup>5</sup>`
    
* `0 <= heights[i] <= 10<sup>4</sup>`
    

Solution:

```python
class Solution:
    def largestRectangleArea(self, heights: List[int]) -> int:
        maxArea = 0
        stack = []  # pair: (index, height)

        for i, h in enumerate(heights):
            start = i
            while stack and stack[-1][1] > h:
                index, height = stack.pop()
                maxArea = max(maxArea, height * (i - index))
                start = index
            stack.append((start, h))

        for i, h in stack:
            maxArea = max(maxArea, h * (len(heights) - i))
        return maxArea
```