---
title: "String Encode and Decode"
datePublished: Sat Jul 06 2024 13:52:04 GMT+0000 (Coordinated Universal Time)
cuid: clya6of3y000209mnbyto1jd2
slug: string-encode-and-decode
tags: dsa

---

Design an algorithm to encode a list of strings to a single string. The encoded string is then decoded back to the original list of strings.

Please implement `encode` and `decode`

**Example 1:**

```java
Input: ["neet","code","love","you"]

Output:["neet","code","love","you"]
```

**Copy**

**Example 2:**

```java
Input: ["we","say",":","yes"]

Output: ["we","say",":","yes"]
```

**Copy**

**Constraints:**

* `0 <= strs.length < 100`
    
* `0 <= strs[i].length < 200`
    
* `strs[i]` contains only UTF-8 characters.
    

Solution:

```python
class Solution:

    def encode(self, strs: List[str]) -> str:
        res = ""
        for s in strs:
            res += str(len(s)) + "#" + s
        return res


    def decode(self, s: str) -> List[str]:
        res = []
        i = 0
        
        while i < len(s):
            # to get the length of the message
            j = i
            while s[j] != '#':
                j += 1

            length = int(s[i:j])
            # to get the message
            i = j + 1
            j = i + length
            res.append(s[i:j])
            # put the i pointer to the next message length
            i = j
            
        return res
```