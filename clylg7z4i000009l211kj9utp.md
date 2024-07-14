---
title: "1071. Greatest Common Divisor of Strings"
datePublished: Sun Jul 14 2024 11:04:41 GMT+0000 (Coordinated Universal Time)
cuid: clylg7z4i000009l211kj9utp
slug: 1071-greatest-common-divisor-of-strings
tags: dsa

---

For two strings `s` and `t`, we say "`t` divides `s`" if and only if `s = t + t + t + ... + t + t` (i.e., `t` is concatenated with itself one or more times).

Given two strings `str1` and `str2`, return *the largest string* `x` *such that* `x` *divides both* `str1` *and* `str2`.

**Example 1:**

```python
Input: str1 = "ABCABC", str2 = "ABC"
Output: "ABC"
```

**Example 2:**

```python
Input: str1 = "ABABAB", str2 = "ABAB"
Output: "AB"
```

**Example 3:**

```python
Input: str1 = "LEET", str2 = "CODE"
Output: ""
```

**Constraints:**

* `1 <= str1.length, str2.length <= 1000`
    
* `str1` and `str2` consist of English uppercase letters.
    

Solution:

```python
class Solution:
    def gcdOfStrings(self, str1: str, str2: str) -> str:
        len1, len2 = len(str1), len(str2)
        
        def isDivisor(l):
            if len1 % l or len2 % l:
                return False

            f1, f2 = len1 // l , len2 // l
            return str1[:l]*f1 == str1 and str1[:l]*f2 == str2

        for l in range(min(len1, len2), 0, -1):
            if isDivisor(l):
                return str1[:l]
        
        return ""
```