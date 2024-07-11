---
title: "647. Palindromic Substrings"
datePublished: Thu Jul 11 2024 13:42:20 GMT+0000 (Coordinated Universal Time)
cuid: clyhbj5yi00050albci3fdi0l
slug: 647-palindromic-substrings
tags: dsa

---

Given a string `s`, return *the number of* ***palindromic substrings*** *in it*.

A string is a **palindrome** when it reads the same backward as forward.

A **substring** is a contiguous sequence of characters within the string.

**Example 1:**

```python
Input: s = "abc"
Output: 3
Explanation: Three palindromic strings: "a", "b", "c".
```

**Example 2:**

```python
Input: s = "aaa"
Output: 6
Explanation: Six palindromic strings: "a", "a", "a", "aa", "aa", "aaa".
```

**Constraints:**

* `1 <= s.length <= 1000`
    
* `s` consists of lowercase English letters.
    

Solution:

```python
class Solution:
    
    def countSubstrings(self, s: str) -> int:
        res = 0

        for i in range(len(s)):
            res += self.countPali(s, i, i)
            res += self.countPali(s, i, i + 1)
        return res

    def countPali(self, s, l, r):
        res = 0
        while l >= 0 and r < len(s) and s[l] == s[r]:
            res += 1
            l -= 1
            r += 1
        return res
```