---
title: "The Two Sum problem"
datePublished: Sat Jan 06 2024 10:01:05 GMT+0000 (Coordinated Universal Time)
cuid: clr1wacnp000109jsesm72fd9
slug: the-two-sum-problem
tags: leetcode

---

# **problem:**

The Two Sum problem asks us to find two numbers in an array that sum up to a given target value. We need to return the indices of these two numbers.

# **Solution:**

1. One brute force approach is to consider every pair of elements and check if their sum equals the target. This can be done using nested loops, where the outer loop iterates from the first element to the second-to-last element, and the inner loop iterates from the next element to the last element. However, this approach has a time complexity of O(n^2).
    
2. A more efficient approach is to use a hash table ( in C++). We can iterate through the array once, and for each element, check if the target minus the current element exists in the hash table. If it does, we have found a valid pair of numbers. If not, we add the current element to the hash table.
    

**An approach using a hash table:**

1. Create an empty hash table to store elements and their indices.
    
2. Iterate through the array from left to right.
    
3. For each element nums\[i\], calculate the complement by subtracting it from the target: complement = target - nums\[i\].
    
4. Check if the complement exists in the hash table. If it does, we have found a solution.
    
5. If the complement does not exist in the hash table, add the current element nums\[i\] to the hash table with its index as the value.
    
6. Repeat steps 3-5 until we find a solution or reach the end of the array.
    
7. If no solution is found, return an empty array or an appropriate indicator.
    

This approach has a time complexity of O(n) since hash table lookups take constant time on average. It allows us to solve the Two Sum problem efficiently by making just one pass through the array.

# **Solution 1: (Brute Force)**

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        n = len(nums)
        for i in range(n - 1):
            for j in range(i + 1, n):
                if nums[i] + nums[j] == target:
                    return [i, j]
        return []  # No solution found
```

# **Solution 2: (Two-pass Hash Table)**

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numMap = {}
        n = len(nums)

        # Build the hash table
        for i in range(n):
            numMap[nums[i]] = i

        # Find the complement
        for i in range(n):
            complement = target - nums[i]
            if complement in numMap and numMap[complement] != i:
                return [i, numMap[complement]]

        return []  # No solution found
```

# **Solution 3: (One-pass Hash Table)**

```python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        numMap = {}
        n = len(nums)

        for i in range(n):
            complement = target - nums[i]
            if complement in numMap:
                return [numMap[complement], i]
            numMap[nums[i]] = i

        return []  # No solution found
```

thankyou