---
title: "48. Rotate Image"
datePublished: Thu Jul 11 2024 12:59:24 GMT+0000 (Coordinated Universal Time)
cuid: clyh9zyrf000f09l8cr9zbzq0
slug: 48-rotate-image
tags: dsa

---

You are given an `n x n` 2D `matrix` representing an image, rotate the image by **90** degrees (clockwise).

You have to rotate the image [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm), which means you have to modify the input 2D matrix directly. **DO NOT** allocate another 2D matrix and do the rotation.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720702500315/c12d0808-e923-43e3-bbf5-f1243d0d45e6.jpeg align="center")

```python
Input: matrix = [[1,2,3],[4,5,6],[7,8,9]]
Output: [[7,4,1],[8,5,2],[9,6,3]]
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720702517529/76777b9d-d081-4113-ad96-bdb1086028c6.jpeg align="center")

```python
Input: matrix = [[5,1,9,11],[2,4,8,10],[13,3,6,7],[15,14,12,16]]
Output: [[15,13,2,5],[14,3,4,1],[12,6,8,9],[16,7,10,11]]
```

**Constraints:**

* `n == matrix.length == matrix[i].length`
    
* `1 <= n <= 20`
    
* `-1000 <= matrix[i][j] <= 1000`
    

Solution:

```python
class Solution:
    def rotate(self, matrix: List[List[int]]) -> None:
        l, r = 0, len(matrix) - 1
        while l < r:
            for i in range(r - l):
                top, bottom = l, r

                # save the topleft
                topLeft = matrix[top][l + i]

                # move bottom left into top left
                matrix[top][l + i] = matrix[bottom - i][l]

                # move bottom right into bottom left
                matrix[bottom - i][l] = matrix[bottom][r - i]

                # move top right into bottom right
                matrix[bottom][r - i] = matrix[top + i][r]

                # move top left into top right
                matrix[top + i][r] = topLeft
            r -= 1
            l += 1
```