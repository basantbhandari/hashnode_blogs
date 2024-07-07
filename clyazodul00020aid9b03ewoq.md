---
title: "Trapping Rain Water"
datePublished: Sun Jul 07 2024 03:23:51 GMT+0000 (Coordinated Universal Time)
cuid: clyazodul00020aid9b03ewoq
slug: trapping-rain-water
tags: dsa

---

Given `n` non-negative integers representing an elevation map where the width of each bar is `1`, compute how much water it can trap after raining.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720322512617/6c297c87-ae18-49ec-b339-4153bb04aef1.png align="center")

```python
Input: height = [0,1,0,2,1,0,1,3,2,1,2,1]
Output: 6
Explanation: The above elevation map (black section) is represented by array [0,1,0,2,1,0,1,3,2,1,2,1]. In this case, 6 units of rain water (blue section) are being trapped.
```

**Example 2:**

```python
Input: height = [4,2,0,3,2,5]
Output: 9
```

**Constraints:**

* `n == height.length`
    
* `1 <= n <= 2 * 10<sup>4</sup>`
    
* `0 <= height[i] <= 10<sup>5</sup>`  
    

solution:

```python
class Solution:
    def trap(self, height: List[int]) -> int:
        # base case
        if not height:
            return 0

        # two pointer problem
        l, r = 0, len(height) - 1
        leftMax, rightMax = height[l], height[r]
        res = 0
        while l < r:
            if leftMax < rightMax:
                l += 1
                leftMax = max(leftMax, height[l])
                res += leftMax - height[l]
            else:
                r -= 1
                rightMax = max(rightMax, height[r])
                res += rightMax - height[r]
        return res
```