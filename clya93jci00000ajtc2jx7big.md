---
title: "15. 3Sum"
datePublished: Sat Jul 06 2024 14:59:48 GMT+0000 (Coordinated Universal Time)
cuid: clya93jci00000ajtc2jx7big
slug: 15-3sum
tags: dsa

---

Given an integer array nums, return all the triplets `[nums[i], nums[j], nums[k]]` such that `i != j`, `i != k`, and `j != k`, and `nums[i] + nums[j] + nums[k] == 0`.

Notice that the solution set must not contain duplicate triplets.

**Example 1:**

```python
Input: nums = [-1,0,1,2,-1,-4]
Output: [[-1,-1,2],[-1,0,1]]
Explanation: 
nums[0] + nums[1] + nums[2] = (-1) + 0 + 1 = 0.
nums[1] + nums[2] + nums[4] = 0 + 1 + (-1) = 0.
nums[0] + nums[3] + nums[4] = (-1) + 2 + (-1) = 0.
The distinct triplets are [-1,0,1] and [-1,-1,2].
Notice that the order of the output and the order of the triplets does not matter.
```

**Example 2:**

```python
Input: nums = [0,1,1]
Output: []
Explanation: The only possible triplet does not sum up to 0.
```

**Example 3:**

```python
Input: nums = [0,0,0]
Output: [[0,0,0]]
Explanation: The only possible triplet sums up to 0.
```

**Constraints:**

* `3 <= nums.length <= 3000`
    
* `-10<sup>5</sup> <= nums[i] <= 10<sup>5</sup>`
    

```python
class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        res = []
        # sort to reduce the time complexity from n3 to n2
        nums.sort()

        for i, a in enumerate(nums):
            # check for duplicate by compairing to the previous element
            if i > 0 and a == nums[i - 1]:
                continue

            # problem is reduced to two sum 2
            l, r = i + 1, len(nums) - 1
            while l < r:
                threeSum = a + nums[l] + nums[r]
                if threeSum > 0:
                    r -= 1
                elif threeSum < 0:
                    l += 1
                else:
                    res.append([a, nums[l], nums[r]])
                    l += 1
                    r -= 1
                    # tackle for duplicate
                    while nums[l] == nums[l - 1] and l < r:
                        l += 1
                        
        return res
```