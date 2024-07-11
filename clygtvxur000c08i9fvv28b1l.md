---
title: "Graph Valid Tree"
datePublished: Thu Jul 11 2024 05:28:23 GMT+0000 (Coordinated Universal Time)
cuid: clygtvxur000c08i9fvv28b1l
slug: graph-valid-tree
tags: dsa

---

Given `n` nodes labeled from `0` to `n - 1` and a list of **undirected** edges (each edge is a pair of nodes), write a function to check whether these edges make up a valid tree.

**Example 1:**

```java
Input:
n = 5
edges = [[0, 1], [0, 2], [0, 3], [1, 4]]

Output:
true
```

**Copy**

**Example 2:**

```java
Input:
n = 5
edges = [[0, 1], [1, 2], [2, 3], [1, 3], [1, 4]]

Output:
false
```

**Copy**

**Note:**

* **You can assume that no duplicate edges will appear in edges. Since all edges are** `undirected`, `[0, 1]` is the same as `[1, 0]` and thus will not appear together in edges.
    

**Constraints:**

* `1 <= n <= 100`
    
* `0 <= edges.length <= n * (n - 1) / 2`
    

Solution:

```python
class Solution:
    def validTree(self, n: int, edges: List[List[int]]) -> bool:
        """
        graph is valid tree only if no loop all connected
        """
        if not n:
            return True
        
        # adj list
        adj = {i: [] for i in range(n)}
        for n1, n2 in edges:
            adj[n1].append(n2)
            adj[n2].append(n1)


        visit = set()
        def dfs(i: int, prev: int) -> bool:
            # check for the loop
            if i in visit:
                return False

            visit.add(i)
            # run DFS for all adj node for particular node except prev
            for j in adj[i]:
                if j == prev:
                    continue
                if not dfs(j, i):
                    return False
            return True

        return dfs(0, -1) and n == len(visit)
    
```