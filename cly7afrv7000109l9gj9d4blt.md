---
title: "217. Contains Duplicate"
datePublished: Thu Jul 04 2024 13:14:00 GMT+0000 (Coordinated Universal Time)
cuid: cly7afrv7000109l9gj9d4blt
slug: 217-contains-duplicate
tags: arrays-hashing

---

Given an integer array `nums`, return `true` if any value appears **at least twice** in the array, and return `false` if every element is distinct.

**Example 1:**

```plaintext
Input: nums = [1,2,3,1]
Output: true
```

**Example 2:**

```plaintext
Input: nums = [1,2,3,4]
Output: false
```

**Example 3:**

```plaintext
Input: nums = [1,1,1,3,3,4,3,2,4,2]
Output: true
```

**Constraints:**

* `1 <= nums.length <= 10<sup>5</sup>`
    
* `-10<sup>9</sup> <= nums[i] <= 10<sup>9</sup>`
    

  

Solution:

```python
class Solution:
    def containsDuplicate(self, nums: List[int]) -> bool:
        hashset = set()
        for n in nums:
           if n in hashset:
               return True
           hashset.add(n)
        return False
```