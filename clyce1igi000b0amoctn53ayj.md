---
title: "21. Merge Two Sorted Lists"
datePublished: Mon Jul 08 2024 02:53:44 GMT+0000 (Coordinated Universal Time)
cuid: clyce1igi000b0amoctn53ayj
slug: 21-merge-two-sorted-lists
tags: dsa

---

You are given the heads of two sorted linked lists `list1` and `list2`.

Merge the two lists into one **sorted** list. The list should be made by splicing together the nodes of the first two lists.

Return *the head of the merged linked list*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720406392655/4b0e7a6d-af5d-4597-9b5b-9b3574ca4468.jpeg align="center")

```python
Input: list1 = [1,2,4], list2 = [1,3,4]
Output: [1,1,2,3,4,4]
```

**Example 2:**

```python
Input: list1 = [], list2 = []
Output: []
```

**Example 3:**

```python
Input: list1 = [], list2 = [0]
Output: [0]
```

**Constraints:**

* The number of nodes in both lists is in the range `[0, 50]`.
    
* `-100 <= Node.val <= 100`
    
* Both `list1` and `list2` are sorted in **non-decreasing** order.
    

Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def mergeTwoLists(self, list1: Optional[ListNode], list2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = node = ListNode()

        while list1 and list2:
            if list1.val < list2.val:
                node.next = list1
                list1 = list1.next
            else:
                node.next = list2
                list2 = list2.next
            node = node.next

        node.next = list1 or list2

        return dummy.next

        
```