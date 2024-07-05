---
title: "242. Valid Anagram"
datePublished: Fri Jul 05 2024 03:01:02 GMT+0000 (Coordinated Universal Time)
cuid: cly83zch200050ajz4m2efyi7
slug: 242-valid-anagram
tags: dsa

---

Given two strings `s` and `t`, return `true` *if* `t` *is an anagram of* `s`*, and* `false` *otherwise*.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

```python
Input: s = "anagram", t = "nagaram"
Output: true
```

**Example 2:**

```python
Input: s = "rat", t = "car"
Output: false
```

**Constraints:**

* `1 <= s.length, t.length <= 5 * 10<sup>4</sup>`
    
* `s` and `t` consist of lowercase English letters.
    

Solution:

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        # solution 1
        # return sorted(s) == sorted(t)

        # solution 2
        # return Counter(s) == Counter(t)

        # solution 3
        if len(s) != len(t):
            return False

        countS, countT = {}, {}

        for i in range(len(s)):
            countS[s[i]] = 1 + countS.get(s[i],0)
            countT[t[i]] = 1 + countT.get(t[i],0)
        
        for c in countS:
            if countS[c] != countT.get(c,0):
                return False
        
        return True
```