---
title: "572. Subtree of Another Tree"
datePublished: Tue Jul 09 2024 02:35:18 GMT+0000 (Coordinated Universal Time)
cuid: clydstn6k000009jo9unk5wux
slug: 572-subtree-of-another-tree
tags: dfs

---

Given the roots of two binary trees `root` and `subRoot`, return `true` if there is a subtree of `root` with the same structure and node values of `subRoot` and `false` otherwise.

A subtree of a binary tree `tree` is a tree that consists of a node in `tree` and all of this node's descendants. The tree `tree` could also be considered as a subtree of itself.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720492214268/435e00aa-4ee1-4fc3-a614-b55bf1997ca8.jpeg align="center")

```python
Input: root = [3,4,5,1,2], subRoot = [4,1,2]
Output: true
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720492230434/4d191b3a-c12b-4426-9a6a-5081b27f8a61.jpeg align="center")

```python
Input: root = [3,4,5,1,2,null,null,null,null,0], subRoot = [4,1,2]
Output: false
```

**Constraints:**

* The number of nodes in the `root` tree is in the range `[1, 2000]`.
    
* The number of nodes in the `subRoot` tree is in the range `[1, 1000]`.
    
* `-10<sup>4</sup> <= root.val <= 10<sup>4</sup>`
    
* `-10<sup>4</sup> <= subRoot.val <= 10<sup>4</sup>`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    
    def isSubtree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        # base cases
        if not subRoot:
            return True
        if not root:
            return False
        # recursive DFS
        if self.sameTree(root, subRoot):
            return True
        # check left and right branch of tree recursively DFS
        return self.isSubtree(root.left, subRoot) or self.isSubtree(root.right, subRoot)

    def sameTree(self, root: Optional[TreeNode], subRoot: Optional[TreeNode]) -> bool:
        if not root and not subRoot:
            return True
        if root and subRoot and root.val == subRoot.val:
            return self.sameTree(root.left, subRoot.left) and self.sameTree(root.right, subRoot.right)
        return False
```