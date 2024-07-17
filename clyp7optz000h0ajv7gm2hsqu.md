---
title: "151. Reverse Words in a String"
datePublished: Wed Jul 17 2024 02:16:50 GMT+0000 (Coordinated Universal Time)
cuid: clyp7optz000h0ajv7gm2hsqu
slug: 151-reverse-words-in-a-string
tags: dsa

---

A **word** is defined as a sequence of non-space characters. The **words** in `s` will be separated by at least one space.

Return *a string of the words in reverse order concatenated by a single space.*

**Note** that `s` may contain leading or trailing spaces or multiple spaces between two words. The returned string should only have a single space separating the words. Do not include any extra spaces.

**Example 1:**

```python
Input: s = "the sky is blue"
Output: "blue is sky the"
```

**Example 2:**

```python
Input: s = "  hello world  "
Output: "world hello"
Explanation: Your reversed string should not contain leading or trailing spaces.
```

**Example 3:**

```python
Input: s = "a good   example"
Output: "example good a"
Explanation: You need to reduce multiple spaces between two words to a single space in the reversed string.
```

**Constraints:**

* `1 <= s.length <= 10<sup>4</sup>`
    
* `s` contains English letters (upper-case and lower-case), digits, and spaces `' '`.
    
* There is **at least one** word in `s`.
    

Solution:

```python
class Solution(object):
    def reverseWords(self, s):
        length = len(s)
        word_positions = []  # To store start and end indices of words
        
        i = 0
        # Iterate through the string to identify word boundaries
        while i < length:
            # Skip leading spaces
            while i < length and s[i] == ' ':
                i += 1
            if i == length:
                break
            
            start = i  # Start of the word
            
            # Move to the end of the word
            while i < length and s[i] != ' ':
                i += 1
            end = i - 1  # End of the word
            
            # Store the start and end indices of the word
            word_positions.append((start, end))
        
        result = []
        # Reverse the order of the words and build the result string
        for start, end in reversed(word_positions):
            word = s[start:end + 1]
            result.append(word)
        
        return ' '.join(result)
```