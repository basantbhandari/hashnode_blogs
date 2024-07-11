---
title: "207. Course Schedule"
datePublished: Thu Jul 11 2024 03:21:28 GMT+0000 (Coordinated Universal Time)
cuid: clygpcqcq000209lcbxfg96dw
slug: 207-course-schedule
tags: dsa

---

There are a total of `numCourses` courses you have to take, labeled from `0` to `numCourses - 1`. You are given an array `prerequisites` where `prerequisites[i] = [a<sub>i</sub>, b<sub>i</sub>]` indicates that you **must** take course `b<sub>i</sub>` first if you want to take course `a<sub>i</sub>`.

* For example, the pair `[0, 1]`, indicates that to take course `0` you have to first take course `1`.
    

Return `true` if you can finish all courses. Otherwise, return `false`.

**Example 1:**

```python
Input: numCourses = 2, prerequisites = [[1,0]]
Output: true
Explanation: There are a total of 2 courses to take. 
To take course 1 you should have finished course 0. So it is possible.
```

**Example 2:**

```python
Input: numCourses = 2, prerequisites = [[1,0],[0,1]]
Output: false
Explanation: There are a total of 2 courses to take. 
To take course 1 you should have finished course 0, and to take course 0 you should also have finished course 1. So it is impossible.
```

**Constraints:**

* `1 <= numCourses <= 2000`
    
* `0 <= prerequisites.length <= 5000`
    
* `prerequisites[i].length == 2`
    
* `0 <= a<sub>i</sub>, b<sub>i</sub> < numCourses`
    
* All the pairs prerequisites\[i\] are **unique**.
    

Solution:

```python
class Solution:
    def canFinish(self, numCourses: int, prerequisites: List[List[int]]) -> bool:
        
        # find the adjacency list
        preMap = {i: [] for i in range(numCourses)}
        for crs, pre in prerequisites:
            preMap[crs].append(pre)

        # to detect the loop
        visiting = set()

        def dfs(crs):
            # base case
            if crs in visiting:
                return False
            if preMap[crs] == []:
                return True

            visiting.add(crs)
            for pre in preMap[crs]:
                # run DFS on pre requisite
                if not dfs(pre):
                    return False
            visiting.remove(crs)
            # if course completed
            preMap[crs] = []
            return True

        for c in range(numCourses):
            if not dfs(c):
                return False
        return True
```