---
title: "74. Search a 2D Matrix"
datePublished: Sun Jul 07 2024 07:59:39 GMT+0000 (Coordinated Universal Time)
cuid: clyb9j2e7000d0ale9bk70dhw
slug: 74-search-a-2d-matrix
tags: dsa

---

You are given an `m x n` integer matrix `matrix` with the following two properties:

* Each row is sorted in non-decreasing order.
    
* The first integer of each row is greater than the last integer of the previous row.
    

Given an integer `target`, return `true` *if* `target` *is in* `matrix` *or* `false` *otherwise*.

You must write a solution in `O(log(m * n))` time complexity.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720338864821/f4a40927-3ca7-4657-b689-05937b796b5b.jpeg align="center")

```python
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Output: true
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720338887365/2bd73000-b733-4990-a6e2-dd592067872e.jpeg align="center")

```python
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false
```

**Constraints:**

* `m == matrix.length`
    
* `n == matrix[i].length`
    
* `1 <= m, n <= 100`
    
* `-10<sup>4</sup> <= matrix[i][j], target <= 10<sup>4</sup>`
    

Solution:

```python
class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        """
        double binary search
        """
        ROWS, COLS = len(matrix), len(matrix[0])

        # determine the row
        top, bot = 0, ROWS - 1
        while top <= bot:
            row = (top + bot) // 2
            if target > matrix[row][-1]:
                top = row + 1
            elif target < matrix[row][0]:
                bot = row - 1
            else:
                break

        # check is the row not found
        if not (top <= bot):
            return False


        # get the row
        row = (top + bot) // 2
        # get the value in the selected row
        # if the target value found return True else False
        l, r = 0, COLS - 1
        while l <= r:
            m = (l + r) // 2
            if target > matrix[row][m]:
                l = m + 1
            elif target < matrix[row][m]:
                r = m - 1
            else:
                return True
        return False
```