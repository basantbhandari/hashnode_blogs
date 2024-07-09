---
title: "230. Kth Smallest Element in a BST"
datePublished: Tue Jul 09 2024 04:43:08 GMT+0000 (Coordinated Universal Time)
cuid: clydxe1x8000109l5g9j9bopx
slug: 230-kth-smallest-element-in-a-bst
tags: dsa

---

Given the `root` of a binary search tree, and an integer `k`, return *the* `k<sup>th</sup>` *smallest value (****1-indexed****) of all the values of the nodes in the tree*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720497066524/b5cb6e4e-2f2b-4b9e-a872-416eedd09791.jpeg align="center")

```python
Input: root = [3,1,4,null,2], k = 1
Output: 1
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720497087266/70a7246e-0bab-41ad-9341-1420b50ebbca.jpeg align="center")

```python
Input: root = [5,3,6,2,4,null,null,1], k = 3
Output: 3
```

**Constraints:**

* The number of nodes in the tree is `n`.
    
* `1 <= k <= n <= 10<sup>4</sup>`
    
* `0 <= Node.val <= 10<sup>4</sup>`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

class Solution:
    def kthSmallest(self, root: Optional[TreeNode], k: int) -> int:
        """
        Iterative in order DFS traversal
        """
        stack = []
        curr = root

        while stack or curr:
            # put the root node in stack and go to the left node as possible
            while curr:
                stack.append(curr)
                curr = curr.left
            # get item from stack LIFO
            curr = stack.pop()
            k -= 1
            # check for the desired element
            if k == 0:
                return curr.val
            # right tree process
            curr = curr.right
```