---
title: "206. Reverse Linked List"
datePublished: Mon Jul 08 2024 02:31:24 GMT+0000 (Coordinated Universal Time)
cuid: clycd8snh000109mjeww1ct1m
slug: 206-reverse-linked-list
tags: dsa

---

Given the `head` of a singly linked list, reverse the list, and return *the reversed list*.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720404184499/d857d4e2-4783-4fae-bf23-0ad478b4791e.jpeg align="center")

```python
Input: head = [1,2,3,4,5]
Output: [5,4,3,2,1]
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720404208162/9aaffe4a-86a0-4373-b904-ae7cd6bae502.jpeg align="center")

```python
Input: head = [1,2]
Output: [2,1]
```

**Example 3:**

```python
Input: head = []
Output: []
```

**Constraints:**

* The number of nodes in the list is the range `[0, 5000]`.
    
* `-5000 <= Node.val <= 5000`
    

**Follow up:** A linked list can be reversed either iteratively or recursively. Could you implement both?

Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        """
        Using iterative (two pointer)
        """
        prev, curr = None, head

        while curr:
            temp = curr.next
            curr.next = prev
            prev = curr
            curr = temp
        return prev





# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        """
        Using recursive approach
        """
        if not head:
            return None
        
        newHead = head
        if head.next:
            newHead = self.reverseList(head.next)
            head.next.next = head
        head.next = None

        return newHead
```