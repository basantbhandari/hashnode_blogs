---
title: "226. Invert Binary Tree"
datePublished: Mon Jul 08 2024 15:12:34 GMT+0000 (Coordinated Universal Time)
cuid: clyd4fn6900030ajw335rbelr
slug: 226-invert-binary-tree
tags: dsa

---

Given the `root` of a binary tree, invert the tree, and return *its root*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720451299228/91c0f19b-d09a-440e-b539-64b9f3618484.jpeg align="center")

```python
Input: root = [4,2,7,1,3,6,9]
Output: [4,7,2,9,6,3,1]
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720451324200/22e443d9-06c7-43b7-872d-86722e2aab99.jpeg align="center")

```python
Input: root = [2,1,3]
Output: [2,3,1]
```

**Example 3:**

```python
Input: root = []
Output: []
```

**Constraints:**

* The number of nodes in the tree is in the range `[0, 100]`.
    
* `-100 <= Node.val <= 100`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def invertTree(self, root: Optional[TreeNode]) -> Optional[TreeNode]:
        if not root: return None

        root.left, root.right = root.right, root.left
        
        self.invertTree(root.left)
        self.invertTree(root.right)
        
        return root
```