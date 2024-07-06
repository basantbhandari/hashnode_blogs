---
title: "49. Group Anagrams"
datePublished: Sat Jul 06 2024 07:41:51 GMT+0000 (Coordinated Universal Time)
cuid: cly9tgbbg00080ajw7q085vxn
slug: 49-group-anagrams
tags: dsa

---

Given an array of strings `strs`, group **the anagrams** together. You can return the answer in **any order**.

An **Anagram** is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

**Example 1:**

```python
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

**Example 2:**

```python
Input: strs = [""]
Output: [[""]]
```

**Example 3:**

```python
Input: strs = ["a"]
Output: [["a"]]
```

**Constraints:**

* `1 <= strs.length <= 10<sup>4</sup>`
    
* `0 <= strs[i].length <= 100`
    
* `strs[i]` consists of lowercase English letters.
    

Solution:

```python
class Solution:
    def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
        ans = defaultdict(list) # mapping charCount to list of anagrams
        for s in strs:
            count = [0] * 26
            for c in s:
                count[ord(c) - ord("a")] += 1
            ans[tuple(count)].append(s)
        return ans.values()
```