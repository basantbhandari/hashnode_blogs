---
title: "Count Connected Components"
datePublished: Thu Jul 11 2024 08:51:24 GMT+0000 (Coordinated Universal Time)
cuid: clyh150w5000g09jmbcx84psd
slug: count-connected-components
tags: dsa

---

There is an undirected graph with `n` nodes. There is also an `edges` array, where `edges[i] = [a, b]` means that there is an edge between node `a` and node `b` in the graph.

Return the total number of connected components in that graph.

**Example 1:**

```java
Input:
n=3
edges=[[0,1], [0,2]]

Output:
1
```

**Copy**

**Example 2:**

```java
Input:
n=6
edges=[[0,1], [1,2], [2,3], [4,5]]

Output:
2
```

**Copy**

**Constraints:**

* `1 <= n <= 100`
    
* `0 <= edges.length <= n * (n - 1) / 2`
    

Solution:

```python
class UnionFind:

    def __init__(self):
        self.f = {}

    def findParent(self, x: int) -> int:
        """
        find the parent of node
        """
        y = self.f.get(x, x)
        if x != y:
            y = self.f[x] = self.findParent(y)
        return y

    def union(self, x: int, y: int):

        self.f[self.findParent(x)] = self.findParent(y)

class Solution:
    def countComponents(self, n: int, edges: List[List[int]]) -> int:
        dsu = UnionFind()
        for a, b in edges:
            dsu.union(a, b)
        return len(set(dsu.findParent(x) for x in range(n)))
    
```