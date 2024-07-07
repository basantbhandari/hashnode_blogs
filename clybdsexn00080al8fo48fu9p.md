---
title: "33. Search in Rotated Sorted Array"
datePublished: Sun Jul 07 2024 09:58:54 GMT+0000 (Coordinated Universal Time)
cuid: clybdsexn00080al8fo48fu9p
slug: 33-search-in-rotated-sorted-array
tags: dsa

---

There is an integer array `nums` sorted in ascending order (with **distinct** values).

Prior to being passed to your function, `nums` is **possibly rotated** at an unknown pivot index `k` (`1 <= k < nums.length`) such that the resulting array is `[nums[k], nums[k+1], ..., nums[n-1], nums[0], nums[1], ..., nums[k-1]]` (**0-indexed**). For example, `[0,1,2,4,5,6,7]` might be rotated at pivot index `3` and become `[4,5,6,7,0,1,2]`.

Given the array `nums` **after** the possible rotation and an integer `target`, return *the index of* `target` *if it is in* `nums`*, or* `-1` *if it is not in* `nums`.

You must write an algorithm with `O(log n)` runtime complexity.

**Example 1:**

```python
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```

**Example 2:**

```python
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```

**Example 3:**

```python
Input: nums = [1], target = 0
Output: -1
```

**Constraints:**

* `1 <= nums.length <= 5000`
    
* `-10<sup>4</sup> <= nums[i] <= 10<sup>4</sup>`
    
* All values of `nums` are **unique**.
    
* `nums` is an ascending array that is possibly rotated.
    
* `-10<sup>4</sup> <= target <= 10<sup>4</sup>`
    

Solutions:

```python
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        l, r = 0, len(nums) - 1

        while l <= r:
            mid = l+ (r - l) // 2
            # check for the target
            if target == nums[mid]:
                return mid
            # if left value is less then middle value
            # middle value belongs to left sorted portion
            if nums[l] <= nums[mid]:
                # target is greater then middle value
                # search right
                if target > nums[mid] or target < nums[l]:
                    l = mid + 1
                # search left
                else:
                    r = mid - 1
            # if left value is greater then middle value
            # middle value belongs to right sorted portion  
            else:
                # target is less then middle value
                # search left
                if target < nums[mid] or target > nums[r]:
                    r = mid - 1
                # search right 
                else:
                    l = mid + 1
        return -1
```