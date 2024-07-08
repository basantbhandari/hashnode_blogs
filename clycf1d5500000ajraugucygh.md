---
title: "143. Reorder List"
datePublished: Mon Jul 08 2024 03:21:37 GMT+0000 (Coordinated Universal Time)
cuid: clycf1d5500000ajraugucygh
slug: 143-reorder-list
tags: dsa

---

You are given the head of a singly linked-list. The list can be represented as:

```python
L0 → L1 → … → Ln - 1 → Ln
```

*Reorder the list to be on the following form:*

```python
L0 → Ln → L1 → Ln - 1 → L2 → Ln - 2 → …
```

You may not modify the values in the list's nodes. Only nodes themselves may be changed.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720407370403/936c9165-dbe7-49db-83f7-1609e7938aec.jpeg align="center")

  
Input: head = \[1,2,3,4\] Output: \[1,4,2,3\]

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720407389982/ff58a283-41d6-49c1-acdb-329e3cab59fc.jpeg align="center")

```python
Input: head = [1,2,3,4,5]
Output: [1,5,2,4,3]
```

**Constraints:**

* The number of nodes in the list is in the range `[1, 5 * 10<sup>4</sup>]`.
    
* `1 <= Node.val <= 1000`
    

Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def reorderList(self, head: Optional[ListNode]) -> None:
        # traverse to get the first and second half of linkedlist
        slow, fast = head, head.next
        while fast and fast.next:
            slow = slow.next
            fast = fast.next.next

        # reverse the second half of the list
        second = slow.next
        prev = slow.next = None
        while second:
            tmp = second.next
            second.next = prev
            prev = second
            second = tmp

        # join the first half and reverse second half
        first, second = head, prev
        while second:
            tmp1, tmp2 = first.next, second.next
            first.next = second
            second.next = tmp1
            first, second = tmp1, tmp2
```