---
title: "Top K Elements in List"
datePublished: Sat Jul 06 2024 13:23:03 GMT+0000 (Coordinated Universal Time)
cuid: clya5n3uw000k0amafr948ml9
slug: top-k-elements-in-list
tags: dsa

---

Given an integer array `nums` and an integer `k`, return *the* `k` *most frequent elements*. You may return the answer in **any order**.

**Example 1:**

```python
Input: nums = [1,1,1,2,2,3], k = 2
Output: [1,2]
```

**Example 2:**

```python
Input: nums = [1], k = 1
Output: [1]
```

**Constraints:**

* `1 <= nums.length <= 10<sup>5</sup>`
    
* `-10<sup>4</sup> <= nums[i] <= 10<sup>4</sup>`
    
* `k` is in the range `[1, the number of unique elements in the array]`.
    
* It is **guaranteed** that the answer is **unique**.
    

Solution:

```python
class Solution:
    def topKFrequent(self, nums: List[int], k: int) -> List[int]:
        count = {}
        freq = [[] for i in range(len(nums) + 1)]
        for n in nums:
            count[n] = 1 + count.get(n, 0)

        for n, c in count.items():
            freq[c].append(n)

        res = []
        for i in range(len(freq)- 1, 0, -1):
            for n in freq[i]:
                res.append(n)
                if len(res) == k:
                    return res
```