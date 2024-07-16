---
title: "345. Reverse Vowels of a String"
datePublished: Tue Jul 16 2024 08:53:14 GMT+0000 (Coordinated Universal Time)
cuid: clyo6enaa000009lb7w7lfx28
slug: 345-reverse-vowels-of-a-string
tags: dsa

---

Given a string `s`, reverse only all the vowels in the string and return it.

The vowels are `'a'`, `'e'`, `'i'`, `'o'`, and `'u'`, and they can appear in both lower and upper cases, more than once.

**Example 1:**

```python
Input: s = "hello"
Output: "holle"
```

**Example 2:**

```python
Input: s = "leetcode"
Output: "leotcede"
```

**Constraints:**

* `1 <= s.length <= 3 * 10<sup>5</sup>`
    
* `s` consist of **printable ASCII** characters.
    

Solution:

```python
class Solution:
    def reverseVowels(self, s: str) -> str:
        """
        solved using two pointer problem
        """
        s=list(s)
        left=0
        right=len(s)-1

        vowels=set('AEIOUaeiou')
        # loop until left pointer is less then right pointer
        while left<right:
            # shift left pointer toward right until it finds the vowel
            while left<right and s[left] not in vowels:
                left+=1
            # shift right pointer toward left until it finds the vowel
            while left<right and s[right] not in vowels:
                right-=1
            # interchange the vowel char
            s[left],s[right]=s[right],s[left]
            # update left and right pointer
            left+=1
            right-=1

        return ''.join(s)
```