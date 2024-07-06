---
title: "Longest Consecutive Sequence"
datePublished: Sat Jul 06 2024 14:37:03 GMT+0000 (Coordinated Universal Time)
cuid: clya8aa8o000109la1gs581um
slug: longest-consecutive-sequence
tags: dsa

---

Given an unsorted array of integers `nums`, return *the length of the longest consecutive elements sequence.*

You must write an algorithm that runs in `O(n)` time.

**Example 1:**

```python
Input: nums = [100,4,200,1,3,2]
Output: 4
Explanation: The longest consecutive elements sequence is [1, 2, 3, 4]. Therefore its length is 4.
```

**Example 2:**

```python
Input: nums = [0,3,7,2,5,8,4,6,0,1]
Output: 9
```

**Constraints:**

* `0 <= nums.length <= 10<sup>5</sup>`
    
* `-10<sup>9</sup> <= nums[i] <= 10<sup>9</sup>`
    

Solutions:

```python
class Solution:
    def longestConsecutive(self, nums: List[int]) -> int:
        numSet = set(nums)
        longest = 0

        for n in numSet:
            # find the start of the sequence
            if (n - 1) not in numSet:
                length = 1
                while (n + length) in numSet:
                    length += 1
                # find the length of largest sequence
                longest = max(length, longest)

        return longest
```