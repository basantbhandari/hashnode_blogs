---
title: "17. Letter Combinations of a Phone Number"
datePublished: Wed Jul 10 2024 06:08:41 GMT+0000 (Coordinated Universal Time)
cuid: clyffvwre000709me94w1bqg2
slug: 17-letter-combinations-of-a-phone-number
tags: dsa

---

Given a string containing digits from `2-9` inclusive, return all possible letter combinations that the number could represent. Return the answer in **any order**.

A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720590841798/e9104763-7b49-4d63-9532-7c94e52faa66.png align="center")

**Example 1:**

```python
Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
```

**Example 2:**

```python
Input: digits = ""
Output: []
```

**Example 3:**

```python
Input: digits = "2"
Output: ["a","b","c"]
```

**Constraints:**

* `0 <= digits.length <= 4`
    
* `digits[i]` is a digit in the range `['2', '9']`.
    

Solution:

```python
class Solution:
    def letterCombinations(self, digits: str) -> List[str]:
        res = []
        digitToChar = {
            "2": "abc",
            "3": "def",
            "4": "ghi",
            "5": "jkl",
            "6": "mno",
            "7": "qprs",
            "8": "tuv",
            "9": "wxyz",
        }

        def backtrack(i, curStr):
            # base case
            if len(curStr) == len(digits):
                res.append(curStr)
                return

            for c in digitToChar[digits[i]]:
                backtrack(i + 1, curStr + c)

        # initiate the backtrack if digits
        if digits:
            backtrack(0, "")

        return res
```