---
title: "100. Same Tree"
datePublished: Tue Jul 09 2024 02:28:28 GMT+0000 (Coordinated Universal Time)
cuid: clydskv8000010ale7ramet69
slug: 100-same-tree
tags: dsa

---

Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.

Two binary trees are considered the same if they are structurally identical, and the nodes have the same value.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720491927602/f16bf25c-709f-4150-9bf4-31f21b6a30c7.jpeg align="center")

```python
Input: p = [1,2,3], q = [1,2,3]
Output: true
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720491945910/0a2d190b-7b64-4bea-a27e-b692e75429b0.jpeg align="center")

```python
Input: p = [1,2], q = [1,null,2]
Output: false
```

**Example 3:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720491963585/c18f21cf-3e06-41d4-9481-0ff2898534c2.jpeg align="center")

```python
Input: p = [1,2,1], q = [1,1,2]
Output: false
```

**Constraints:**

* The number of nodes in both trees is in the range `[0, 100]`.
    
* `-10<sup>4</sup> <= Node.val <= 10<sup>4</sup>`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
# recursive DFS
class Solution:
    def isSameTree(self, p: Optional[TreeNode], q: Optional[TreeNode]) -> bool:
        if not p and not q:
            return True
        if p and q and p.val == q.val:
            return self.isSameTree(p.left, q.left) and self.isSameTree(p.right, q.right)
        else:
            return False
```