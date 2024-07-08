---
title: "2. Add Two Numbers"
datePublished: Mon Jul 08 2024 12:39:17 GMT+0000 (Coordinated Universal Time)
cuid: clycyyj7400050alb6gns2vtc
slug: 2-add-two-numbers
tags: dsa

---

You are given two **non-empty** linked lists representing two non-negative integers. The digits are stored in **reverse order**, and each of their nodes contains a single digit. Add the two numbers and return the sum as a linked list.

You may assume the two numbers do not contain any leading zero, except the number 0 itself.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720441704958/576393a1-2844-4665-a792-5a0bfc787d2b.jpeg align="center")

```python
Input: l1 = [2,4,3], l2 = [5,6,4]
Output: [7,0,8]
Explanation: 342 + 465 = 807.
```

**Example 2:**

```python
Input: l1 = [0], l2 = [0]
Output: [0]
```

**Example 3:**

```python
Input: l1 = [9,9,9,9,9,9,9], l2 = [9,9,9,9]
Output: [8,9,9,9,0,0,0,1]
```

**Constraints:**

* The number of nodes in each linked list is in the range `[1, 100]`.
    
* `0 <= Node.val <= 9`
    
* It is guaranteed that the list represents a number that does not have leading zeros.
    

Solution:

```python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, val=0, next=None):
#         self.val = val
#         self.next = next

class Solution:
    def addTwoNumbers(self, l1: Optional[ListNode], l2: Optional[ListNode]) -> Optional[ListNode]:
        dummy = ListNode()
        cur = dummy

        carry = 0
        while l1 or l2 or carry:
            # get the digit value
            v1 = l1.val if l1 else 0
            v2 = l2.val if l2 else 0

            # new digit
            val = v1 + v2 + carry
            carry = val // 10
            val = val % 10
            cur.next = ListNode(val)

            # update ptrs
            cur = cur.next
            l1 = l1.next if l1 else None
            l2 = l2.next if l2 else None

        return dummy.next
 
```