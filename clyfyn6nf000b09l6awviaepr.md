---
title: "994. Rotting Oranges"
datePublished: Wed Jul 10 2024 14:53:46 GMT+0000 (Coordinated Universal Time)
cuid: clyfyn6nf000b09l6awviaepr
slug: 994-rotting-oranges
tags: dsa

---

You are given an `m x n` `grid` where each cell can have one of three values:

* `0` representing an empty cell,
    
* `1` representing a fresh orange, or
    
* `2` representing a rotten orange.
    

Every minute, any fresh orange that is **4-directionally adjacent** to a rotten orange becomes rotten.

Return *the minimum number of minutes that must elapse until no cell has a fresh orange*. If *this is impossible, return* `-1`.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720622473996/3aeb70c3-3e2f-432d-a800-2e1e5c63ec78.png align="center")

```python
Input: grid = [[2,1,1],[1,1,0],[0,1,1]]
Output: 4
```

**Example 2:**

```python
Input: grid = [[2,1,1],[0,1,1],[1,0,1]]
Output: -1
Explanation: The orange in the bottom left corner (row 2, column 0) is never rotten, because rotting only happens 4-directionally.
```

**Example 3:**

```python
Input: grid = [[0,2]]
Output: 0
Explanation: Since there are already no fresh oranges at minute 0, the answer is just 0.
```

**Constraints:**

* `m == grid.length`
    
* `n == grid[i].length`
    
* `1 <= m, n <= 10`
    
* `grid[i][j]` is `0`, `1`, or `2`.
    

Solution:

```python
class Solution:
    def orangesRotting(self, grid: List[List[int]]) -> int:
        """
        BFS iterative
        """
        q = collections.deque()
        fresh = 0
        time = 0

        # initialize fresh and rotton orange
        for r in range(len(grid)):
            for c in range(len(grid[0])):
                # frash orange
                if grid[r][c] == 1:
                    fresh += 1
                # rotton orange
                if grid[r][c] == 2:
                    q.append((r, c))

        # for all direction
        directions = [[0, 1], [0, -1], [1, 0], [-1, 0]]


        while fresh > 0 and q:
            for i in range(len(q)):

                r, c = q.popleft()

                for dr, dc in directions:
                    row, col = r + dr, c + dc
                    
                    if (
                        row in range(len(grid))
                        and col in range(len(grid[0]))
                        and grid[row][col] == 1
                    ):
                        grid[row][col] = 2
                        q.append((row, col))
                        fresh -= 1
            
            time += 1

        return time if fresh == 0 else -1
```