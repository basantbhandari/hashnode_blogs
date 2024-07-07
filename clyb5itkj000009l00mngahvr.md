---
title: "853. Car Fleet"
datePublished: Sun Jul 07 2024 06:07:29 GMT+0000 (Coordinated Universal Time)
cuid: clyb5itkj000009l00mngahvr
slug: 853-car-fleet
tags: dsa

---

There are `n` cars at given miles away from the starting mile 0, traveling to reach the mile `target`.

You are given two integer array `position` and `speed`, both of length `n`, where `position[i]` is the starting mile of the `i<sup>th</sup>` car and `speed[i]` is the speed of the `i<sup>th</sup>` car in miles per hour.

A car cannot pass another car, but it can catch up and then travel next to it at the speed of the slower car.

A **car fleet** is a car or cars driving next to each other. The speed of the car fleet is the **minimum** speed of any car in the fleet.

If a car catches up to a car fleet at the mile `target`, it will still be considered as part of the car fleet.

Return the number of car fleets that will arrive at the destination.

**Example 1:**

**Input:** target = 12, position = \[10,8,0,5,3\], speed = \[2,4,1,1,3\]

**Output:** 3

**Explanation:**

* The cars starting at 10 (speed 2) and 8 (speed 4) become a fleet, meeting each other at 12. The fleet forms at `target`.
    
* The car starting at 0 (speed 1) does not catch up to any other car, so it is a fleet by itself.
    
* The cars starting at 5 (speed 1) and 3 (speed 3) become a fleet, meeting each other at 6. The fleet moves at speed 1 until it reaches `target`.
    

**Example 2:**

**Input:** target = 10, position = \[3\], speed = \[3\]

**Output:** 1

**Explanation:**

There is only one car, hence there is only one fleet.

**Example 3:**

**Input:** target = 100, position = \[0,2,4\], speed = \[4,2,1\]

**Output:** 1

**Explanation:**

* The cars starting at 0 (speed 4) and 2 (speed 2) become a fleet, meeting each other at 4. The car starting at 4 (speed 1) travels to 5.
    
* Then, the fleet at 4 (speed 2) and the car at position 5 (speed 1) become one fleet, meeting each other at 6. The fleet moves at speed 1 until it reaches `target`.
    

**Constraints:**

* `n == position.length == speed.length`
    
* `1 <= n <= 10<sup>5</sup>`
    
* `0 < target <= 10<sup>6</sup>`
    
* `0 <= position[i] < target`
    
* All the values of `position` are **unique**.
    
* `0 < speed[i] <= 10<sup>6</sup>`
    

Solution:

```python
class Solution:
    def carFleet(self, target: int, position: List[int], speed: List[int]) -> int:
        pair = [(p, s) for p, s in zip(position, speed)]
        pair.sort(reverse=True) # Reverse Sorted Order
        stack = []
        for p, s in pair:
            # eval the time for each car
            stack.append((target - p) / s)
            if len(stack) >= 2 and stack[-1] <= stack[-2]:
                stack.pop()
        return len(stack)
```