---
title: "138. Copy List with Random Pointer"
datePublished: Mon Jul 08 2024 12:26:18 GMT+0000 (Coordinated Universal Time)
cuid: clycyhu0l000m09jtfkm589it
slug: 138-copy-list-with-random-pointer
tags: dsa

---

A linked list of length `n` is given such that each node contains an additional random pointer, which could point to any node in the list, or `null`.

Construct a [**deep copy**](https://en.wikipedia.org/wiki/Object_copying#Deep_copy) of the list. The deep copy should consist of exactly `n` **brand new** nodes, where each new node has its value set to the value of its corresponding original node. Both the `next` and `random` pointer of the new nodes should point to new nodes in the copied list such that the pointers in the original list and copied list represent the same list state. **None of the pointers in the new list should point to nodes in the original list**.

For example, if there are two nodes `X` and `Y` in the original list, where `X.random --> Y`, then for the corresponding two nodes `x` and `y` in the copied list, `x.random --> y`.

Return *the head of the copied linked list*.

The linked list is represented in the input/output as a list of `n` nodes. Each node is represented as a pair of `[val, random_index]` where:

* `val`: an integer representing `Node.val`
    
* `random_index`: the index of the node (range from `0` to `n-1`) that the `random` pointer points to, or `null` if it does not point to any node.
    

Your code will **only** be given the `head` of the original linked list.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720409986871/64a0ea0a-309a-43a2-a85b-04b9434e9289.png align="center")

```python
Input: head = [[7,null],[13,0],[11,4],[10,2],[1,0]]
Output: [[7,null],[13,0],[11,4],[10,2],[1,0]]
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720410003411/42edd831-9398-4502-963a-948af1377554.png align="center")

```python
Input: head = [[1,1],[2,1]]
Output: [[1,1],[2,1]]
```

**Example 3:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720410025561/4046cd45-e951-4cb0-8de2-ee0651873a2d.png align="center")

```python
Input: head = [[3,null],[3,0],[3,null]]
Output: [[3,null],[3,0],[3,null]]
```

**Constraints:**

* `0 <= n <= 1000`
    
* `-10<sup>4</sup> <= Node.val <= 10<sup>4</sup>`
    
* `Node.random` is `null` or is pointing to some node in the linked list.
    

Solution:

```python
"""
# Definition for a Node.
class Node:
    def __init__(self, x: int, next: 'Node' = None, random: 'Node' = None):
        self.val = int(x)
        self.next = next
        self.random = random
"""

class Solution:
    def copyRandomList(self, head: 'Optional[Node]') -> 'Optional[Node]':
        oldToCopy = {None: None}

        cur = head
        while cur:
            copy = Node(cur.val)
            oldToCopy[cur] = copy
            cur = cur.next
        cur = head
        while cur:
            copy = oldToCopy[cur]
            copy.next = oldToCopy[cur.next]
            copy.random = oldToCopy[cur.random]
            cur = cur.next
        return oldToCopy[head]
```