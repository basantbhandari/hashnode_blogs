---
title: "1768. Merge Strings Alternately"
datePublished: Sun Jul 14 2024 06:29:47 GMT+0000 (Coordinated Universal Time)
cuid: clyl6egra00020al93tc9abvu
slug: 1768-merge-strings-alternately
tags: dsa

---

You are given two strings `word1` and `word2`. Merge the strings by adding letters in alternating order, starting with `word1`. If a string is longer than the other, append the additional letters onto the end of the merged string.

Return *the merged string.*

**Example 1:**

```python
Input: word1 = "abc", word2 = "pqr"
Output: "apbqcr"
Explanation: The merged string will be merged as so:
word1:  a   b   c
word2:    p   q   r
merged: a p b q c r
```

**Example 2:**

```python
Input: word1 = "ab", word2 = "pqrs"
Output: "apbqrs"
Explanation: Notice that as word2 is longer, "rs" is appended to the end.
word1:  a   b 
word2:    p   q   r   s
merged: a p b q   r   s
```

**Example 3:**

```python
Input: word1 = "abcd", word2 = "pq"
Output: "apbqcd"
Explanation: Notice that as word1 is longer, "cd" is appended to the end.
word1:  a   b   c   d
word2:    p   q 
merged: a p b q c   d
```

**Constraints:**

* `1 <= word1.length, word2.length <= 100`
    
* `word1` and `word2` consist of lowercase English letters.
    

Solution:

```python
class Solution:
    def mergeAlternately(self, word1: str, word2: str) -> str:
        # solution 1
        merged = []
        for a, b in zip(word1, word2):
            merged.append(a + b)
        
        merged.append(word1[len(word2):])
        merged.append(word2[len(word1):])

        return "".join(merged)

        # Solution 2
        i, j = 0, 0
        res = []
        while i < len(word1) and j < len(word2):
            res.append(word1[i])
            res.append(word2[j])
            i += 1
            j += 1
        
        res.append(word1[i:])
        res.append(word2[j:])
        return "".join(res)
```