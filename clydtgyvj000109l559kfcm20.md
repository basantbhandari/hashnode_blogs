---
title: "102. Binary Tree Level Order Traversal"
datePublished: Tue Jul 09 2024 02:53:26 GMT+0000 (Coordinated Universal Time)
cuid: clydtgyvj000109l559kfcm20
slug: 102-binary-tree-level-order-traversal
tags: dsa

---

Given the `root` of a binary tree, return *the level order traversal of its nodes' values*. (i.e., from left to right, level by level).

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720493384922/d7878938-9fd1-4f13-9f29-85314c43e7d5.jpeg align="center")

```python
Input: root = [3,9,20,null,null,15,7]
Output: [[3],[9,20],[15,7]]
```

**Example 2:**

```python
Input: root = [1]
Output: [[1]]
```

**Example 3:**

```python
Input: root = []
Output: []
```

**Constraints:**

* The number of nodes in the tree is in the range `[0, 2000]`.
    
* `-1000 <= Node.val <= 1000`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def levelOrder(self, root: Optional[TreeNode]) -> List[List[int]]:
        """
        Iterative BFS
        """
        res = []
        q = deque()
        if root:
            q.append(root)
        while q:
            val = []
            for i in range(len(q)):
                node = q.popleft()
                val.append(node.val)
                if node.left:
                    q.append(node.left)
                if node.right:
                    q.append(node.right)
            res.append(val)
        return res
```