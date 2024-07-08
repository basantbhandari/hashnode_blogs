---
title: "19. Remove Nth Node From End of List"
datePublished: Mon Jul 08 2024 03:37:11 GMT+0000 (Coordinated Universal Time)
cuid: clycfldov000b0aii98bf169y
slug: 19-remove-nth-node-from-end-of-list
tags: dsa

---

Given the `head` of a linked list, remove the `n<sup>th</sup>` node from the end of the list and return its head.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720409105800/8364c722-ee8d-4fd7-aa6c-3306843488f0.jpeg align="center")

```python
Input: head = [1,2,3,4,5], n = 2
Output: [1,2,3,5]
```

**Example 2:**

```python
Input: head = [1], n = 1
Output: []
```

**Example 3:**

```python
Input: head = [1,2], n = 1
Output: [1]
```

**Constraints:**

* The number of nodes in the list is `sz`.
    
* `1 <= sz <= 30`
    
* `0 <= Node.val <= 100`
    
* `1 <= n <= sz`
    

Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def removeNthFromEnd(self, head: Optional[ListNode], n: int) -> Optional[ListNode]:
        """
        using two pointer approach
        node difference between two pointer must be n
        so we need dummy node
        """
        # create a dummy node which is left pointer
        dummy = ListNode(0, head)
        left = dummy
        # traverse right pointer to node n from head node
        right = head
        while n > 0:
            right = right.next
            n -= 1

        # traverse the left and right pointer by one node at a time until 
        # the end of the linkedlist
        while right:
            left = left.next
            right = right.next
        # left pointer must be pointing the node previous to the 
        # node we need remove
        # remove the n th node from last 
        left.next = left.next.next

        # return the new linked list
        return dummy.next
```