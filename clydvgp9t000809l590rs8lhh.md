---
title: "98. Validate Binary Search Tree"
datePublished: Tue Jul 09 2024 03:49:13 GMT+0000 (Coordinated Universal Time)
cuid: clydvgp9t000809l590rs8lhh
slug: 98-validate-binary-search-tree
tags: dsa

---

Given the `root` of a binary tree, *determine if it is a valid binary search tree (BST)*.

A **valid BST** is defined as follows:

* The left subtree of a node contains only nodes with keys **less than** the node's key.
    
* The right subtree of a node contains only nodes with keys **greater than** the node's key.
    
* Both the left and right subtrees must also be binary search trees.
    

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720496361390/f12caf47-5af9-4d71-9d7a-1e9bebea92c5.jpeg align="center")

```python
Input: root = [2,1,3]
Output: true
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720496399061/c198b857-4e10-4b51-bbff-01cf87a35da3.jpeg align="center")

```python
Input: root = [5,1,4,null,null,3,6]
Output: false
Explanation: The root node's value is 5 but its right child's value is 4.
```

**Constraints:**

* The number of nodes in the tree is in the range `[1, 10<sup>4</sup>]`.
    
* `-2<sup>31</sup> <= Node.val <= 2<sup>31</sup> - 1`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        """
        recursive DFS
        """
        def valid(node, left, right):
            # base case
            if not node:
                return True
            # case where binary search tree case broke
            if not (left < node.val < right):
                return False
            # do recursive call
            return valid(node.left, left, node.val) and 
            valid(node.right, node.val, right)

        return valid(root, float("-inf"), float("inf"))
```