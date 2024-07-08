---
title: "104. Maximum Depth of Binary Tree"
datePublished: Mon Jul 08 2024 16:03:25 GMT+0000 (Coordinated Universal Time)
cuid: clyd691bp00070akv3wc57z9t
slug: 104-maximum-depth-of-binary-tree
tags: dsa

---

Given the `root` of a binary tree, return *its maximum depth*.

A binary tree's **maximum depth** is the number of nodes along the longest path from the root node down to the farthest leaf node.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720451637573/a3e72217-fbee-4b32-9209-ebdf487d185e.jpeg align="center")

```python
Input: root = [3,9,20,null,null,15,7]
Output: 3
```

**Example 2:**

```python
Input: root = [1,null,2]
Output: 2
```

**Constraints:**

* The number of nodes in the tree is in the range `[0, 10<sup>4</sup>]`.
    
* `-100 <= Node.val <= 100`
    

Solution:

```python
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right

# RECURSIVE DFS
class Solution:
    def maxDepth(self, root: Optional[TreeNode]) -> int:
        if not root:
            return 0

        return 1 + max(self.maxDepth(root.left), self.maxDepth(root.right))


# ITERATIVE DFS
# class Solution:
#     def maxDepth(self, root: Optional[TreeNode]) -> int:
#         stack = [[root, 1]]
#         res = 0

#         while stack:
#             node, depth = stack.pop()

#             if node:
#                 res = max(res, depth)
#                 stack.append([node.left, depth + 1])
#                 stack.append([node.right, depth + 1])
#         return res


# ITERATIVE BFS
# class Solution:
#     def maxDepth(self, root: Optional[TreeNode]) -> int:
#         q = deque()
#         if root:
#             q.append(root)

#         level = 0

#         while q:

#             for i in range(len(q)):
#                 node = q.popleft()
#                 if node.left:
#                     q.append(node.left)
#                 if node.right:
#                     q.append(node.right)
#             level += 1
#         return level
```