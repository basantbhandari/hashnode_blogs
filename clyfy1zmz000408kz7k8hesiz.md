---
title: "Islands and Treasure"
datePublished: Wed Jul 10 2024 14:37:17 GMT+0000 (Coordinated Universal Time)
cuid: clyfy1zmz000408kz7k8hesiz
slug: islands-and-treasure
tags: dsa

---

You are given a 𝑚×𝑛*m*×*n* 2D `grid` initialized with these three possible values:

1. `-1` - A water cell that *can not* be traversed.
    
2. `0` - A treasure chest.
    
3. `INF` - A land cell that *can* be traversed. We use the integer `2^31 - 1 = 2147483647` to represent `INF`.
    

Fill each land cell with the distance to its nearest treasure chest. If a land cell cannot reach a treasure chest than the value should remain `INF`.

Assume the grid can only be traversed up, down, left, or right.

**Example 1:**

```java
Input: [
  [2147483647,-1,0,2147483647],
  [2147483647,2147483647,2147483647,-1],
  [2147483647,-1,2147483647,-1],
  [0,-1,2147483647,2147483647]
]

Output: [
  [3,-1,0,1],
  [2,2,1,-1],
  [1,-1,2,-1],
  [0,-1,3,4]
]
```

**Copy**

**Example 2:**

```java
Input: [
  [0,-1],
  [2147483647,2147483647]
]

Output: [
  [0,-1],
  [1,2]
]
```

**Copy**

**Constraints:**

* `m == grid.length`
    
* `n == grid[i].length`
    
* `1 <= m, n <= 100`
    
* `grid[i][j]` is one of `{-1, 0, 2147483647}`
    

Solution:

```python
class Solution:
    def islandsAndTreasure(self, grid: List[List[int]]) -> None:
        """
        BFS iterative solution
        """
        ROWS, COLS = len(grid), len(grid[0])
        visit = set()
        q = deque()

        def addCell(r, c):
            if (
                min(r, c) < 0
                or r == ROWS
                or c == COLS
                or (r, c) in visit
                or grid[r][c] == -1 # wall or obstacle
            ):
                return
            visit.add((r, c))
            q.append([r, c])


        # initialize the queue
        for r in range(ROWS):
            for c in range(COLS):
                # if any call is gate
                if grid[r][c] == 0:
                    # add gate to queue and mark that visited
                    q.append([r, c])
                    visit.add((r, c))


        # do BFS
        dist = 0 # distance
        while q:
            for i in range(len(q)):
                r, c = q.popleft()
                grid[r][c] = dist

                addCell(r + 1, c)
                addCell(r - 1, c)
                addCell(r, c + 1)
                addCell(r, c - 1)
                
            dist += 1
```