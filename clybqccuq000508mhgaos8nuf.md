---
title: "567. Permutation in String"
datePublished: Sun Jul 07 2024 15:50:19 GMT+0000 (Coordinated Universal Time)
cuid: clybqccuq000508mhgaos8nuf
slug: 567-permutation-in-string
tags: dsa

---

Given two strings `s1` and `s2`, return `true` *if* `s2` *contains a permutation of* `s1`*, or* `false` *otherwise*.

In other words, return `true` if one of `s1`'s permutations is the substring of `s2`.

**Example 1:**

```python
Input: s1 = "ab", s2 = "eidbaooo"
Output: true
Explanation: s2 contains one permutation of s1 ("ba").
```

**Example 2:**

```python
Input: s1 = "ab", s2 = "eidboaoo"
Output: false
```

**Constraints:**

* `1 <= s1.length, s2.length <= 10<sup>4</sup>`
    
* `s1` and `s2` consist of lowercase English letters.
    

Solution:

```python
class Solution:
    def checkInclusion(self, s1: str, s2: str) -> bool:
        # basic validation
        if len(s1) > len(s2):
            return False

        # counter for two strings
        s1Count, s2Count = [0] * 26, [0] * 26
        for i in range(len(s1)):
            s1Count[ord(s1[i]) - ord("a")] += 1
            s2Count[ord(s2[i]) - ord("a")] += 1


        # find the match
        matches = 0
        for i in range(26):
            matches += 1 if s1Count[i] == s2Count[i] else 0



        # use sliding window problem
        l = 0
        for r in range(len(s1), len(s2)):
            # if s1 and sub string from s2 matches
            if matches == 26:
                return True

            # adding the char from right
            index = ord(s2[r]) - ord("a")
            s2Count[index] += 1
            if s1Count[index] == s2Count[index]:
                matches += 1
            elif s1Count[index] + 1 == s2Count[index]:
                matches -= 1

            # remove the char from left
            index = ord(s2[l]) - ord("a")
            s2Count[index] -= 1
            if s1Count[index] == s2Count[index]:
                matches += 1
            elif s1Count[index] - 1 == s2Count[index]:
                matches -= 1

            # increase the left pointer
            l += 1

        return matches == 26
```