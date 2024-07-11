---
title: "5. Longest Palindromic Substring"
datePublished: Thu Jul 11 2024 13:28:21 GMT+0000 (Coordinated Universal Time)
cuid: clyhb16rz000208jv65ynel4f
slug: 5-longest-palindromic-substring
tags: dsa

---

Given a string `s`, return *the longest*

*palindromic*

*substring*

in`s`.

**Example 1:**

```python
Input: s = "babad"
Output: "bab"
Explanation: "aba" is also a valid answer.
```

**Example 2:**

```python
Input: s = "cbbd"
Output: "bb"
```

**Constraints:**

* `1 <= s.length <= 1000`
    
* `s` consist of only digits and English letters.
    

Solution:

```python
class Solution:
    def longestPalindrome(self, s: str) -> str:
        res = ""
        resLen = 0

        for i in range(len(s)):
            # odd length
            l, r = i, i
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if (r - l + 1) > resLen:
                    res = s[l : r + 1]
                    resLen = r - l + 1
                l -= 1
                r += 1

            # even length
            l, r = i, i + 1
            while l >= 0 and r < len(s) and s[l] == s[r]:
                if (r - l + 1) > resLen:
                    res = s[l : r + 1]
                    resLen = r - l + 1
                l -= 1
                r += 1

        return res
```