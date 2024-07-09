---
title: "199. Binary Tree Right Side View"
datePublished: Tue Jul 09 2024 03:01:53 GMT+0000 (Coordinated Universal Time)
cuid: clydtrufd000009mi5oiqf7ss
slug: 199-binary-tree-right-side-view
tags: dsa

---

Given the `root` of a binary tree, imagine yourself standing on the **right side** of it, return *the values of the nodes you can see ordered from top to bottom*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720493733474/cae1d999-4672-4ed0-b688-d737ebfd18a4.jpeg align="center")

  
Input: root = \[1,2,3,null,5,null,4\] Output: \[1,3,4\]

**Example 2:**

```python
Input: root = [1,null,3]
Output: [1,3]
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
    def rightSideView(self, root: Optional[TreeNode]) -> List[int]:
        """
        Iterative BFS (Level order traversal)
        """
        res = []
        q = deque()

        if root:
            q.append(root)

        while q:
            rightSide = None
            for i in range(len(q)):
                node = q.popleft()
                if node:
                    rightSide = node
                    q.append(node.left)
                    q.append(node.right)
            if rightSide:
                res.append(rightSide.val)
        return res
```