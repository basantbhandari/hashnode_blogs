---
title: "235. Lowest Common Ancestor of a Binary Search Tree"
datePublished: Tue Jul 09 2024 02:46:24 GMT+0000 (Coordinated Universal Time)
cuid: clydt7xn6000009m6e3e0dnxa
slug: 235-lowest-common-ancestor-of-a-binary-search-tree
tags: dsa

---

Given a binary search tree (BST), find the lowest common ancestor (LCA) node of two given nodes in the BST.

According to the [definition of LCA on Wikipedia](https://en.wikipedia.org/wiki/Lowest_common_ancestor): “The lowest common ancestor is defined between two nodes `p` and `q` as the lowest node in `T` that has both `p` and `q` as descendants (where we allow **a node to be a descendant of itself**).”

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720492782256/d8204967-c430-49cb-8c02-d0e9c3c108a8.png align="center")

```python
Input: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 8
Output: 6
Explanation: The LCA of nodes 2 and 8 is 6.
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720492803197/fcb6ceec-1b63-4b33-8a6d-1ec1b30c8ded.png align="center")

```python
Input: root = [6,2,8,0,4,7,9,null,null,3,5], p = 2, q = 4
Output: 2
Explanation: The LCA of nodes 2 and 4 is 2, since a node can be a descendant of itself according to the LCA definition.
```

**Example 3:**

```python
Input: root = [2,1], p = 2, q = 1
Output: 2
```

**Constraints:**

* The number of nodes in the tree is in the range `[2, 10<sup>5</sup>]`.
    
* `-10<sup>9</sup> <= Node.val <= 10<sup>9</sup>`
    
* All `Node.val` are **unique**.
    
* `p != q`
    
* `p` and `q` will exist in the BST.
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def lowestCommonAncestor(self, root: TreeNode, p: TreeNode, q: TreeNode) -> TreeNode:
        while True:
            if root.val < p.val and root.val < q.val:
                root = root.right
            elif root.val > p.val and root.val > q.val:
                root = root.left
            else:
                return root
```