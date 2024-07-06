---
title: "118. Pascal's Triangle"
datePublished: Sat Jul 06 2024 03:50:10 GMT+0000 (Coordinated Universal Time)
cuid: cly9l6dpt000k08lb78yv3qi7
slug: 118-pascals-triangle
tags: dsa

---

Given an integer `numRows`, return the first numRows of **Pascal's triangle**.

In **Pascal's triangle**, each number is the sum of the two numbers directly above it as shown:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720236943870/483fd15f-0172-46b9-984f-9f9b38251fe4.gif align="center")

**Example 1:**

```plaintext
Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
```

**Example 2:**

```plaintext
Input: numRows = 1
Output: [[1]]
```

Solution:

```python
class Solution:
    def generate(self, numRows: int) -> List[List[int]]:
        """
        two pointer problem
        """
        # base case (first row) in result
        res = [[1]]
        # build the rest row
        for i in range(numRows - 1):
            # for each row, get the last row and append and prepend with 0 
            temp = [0] + res[-1] + [0]
            # each row
            row = []
            # building the each row
            for j in range(len(res[-1]) + 1):
                row.append(temp[j] + temp[j+1])
            res.append(row)
        return res
```