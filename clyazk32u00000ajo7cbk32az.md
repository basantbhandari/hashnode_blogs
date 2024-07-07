---
title: "Container With Most Water"
datePublished: Sun Jul 07 2024 03:20:30 GMT+0000 (Coordinated Universal Time)
cuid: clyazk32u00000ajo7cbk32az
slug: container-with-most-water
tags: dsa

---

You are given an integer array `height` of length `n`. There are `n` vertical lines drawn such that the two endpoints of the `i<sup>th</sup>` line are `(i, 0)` and `(i, height[i])`.

Find two lines that together with the x-axis form a container, such that the container contains the most water.

Return *the maximum amount of water a container can store*.

**Notice** that you may not slant the container.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720278127113/526a4a1e-7aae-4eed-a786-600ff0c58415.jpeg align="center")

```python
Input: height = [1,8,6,2,5,4,8,3,7]
Output: 49
Explanation: The above vertical lines are represented by array [1,8,6,2,5,4,8,3,7]. In this case, the max area of water (blue section) the container can contain is 49.
```

**Example 2:**

```python
Input: height = [1,1]
Output: 1
```

**Constraints:**

* `n == height.length`
    
* `2 <= n <= 10<sup>5</sup>`
    
* `0 <= height[i] <= 10<sup>4</sup>`
    

Solution:

```python
class Solution:
    def maxArea(self, heights: List[int]) -> int:
        l, r = 0, len(heights) - 1
        res = 0

        while l < r:
            res = max(res, min(heights[l], heights[r]) * (r - l))
            if heights[l] < heights[r]:
                l += 1
            elif heights[r] <= heights[l]:
                r -= 1
            
        return res
```