---
title: "Valid Parentheses"
datePublished: Sat Jan 06 2024 11:29:06 GMT+0000 (Coordinated Universal Time)
cuid: clr1zfjg7000809lh3arwfnfq
slug: valid-parentheses
tags: leetcode

---

# **Intuition**

The problem requires us to determine if the given string of brackets is valid or not. We can use a stack data structure to keep track of the opening brackets encountered and check if they match with the corresponding closing brackets.

# **Approach**

Here is the step-by-step approach of the algorithm:

1. Initialize an empty stack.
    
2. Traverse the input string character by character.
    
3. If the current character is an opening bracket (i.e., '(', '{', '\['), push it onto the stack.
    
4. If the current character is a closing bracket (i.e., ')', '}', '\]'), check if the stack is empty. If it is empty, return false, because the closing bracket does not have a corresponding opening bracket. Otherwise, pop the top element from the stack and check if it matches the current closing bracket. If it does not match, return false because the brackets are not valid.
    
5. After traversing the entire input string, if the stack is empty, return true, because all opening brackets have been matched with their corresponding closing brackets. Otherwise, return false, because some opening brackets have not been matched with their corresponding closing brackets.
    

# **Complexity**

* Time complexity:
    

The time complexity of the solution is O(n)O(n)*O*(*n*), where n is the length of the input string. This is because we traverse the string once and perform constant time operations for each character.

* Space complexity:
    

The space complexity of the solution is O(n)O(n)*O*(*n*), where n is the length of the input string. This is because the worst-case scenario is when all opening brackets are present in the string and the stack will have to store them all.

```python
class Solution(object):
    def isValid(self, s):
        stack = [] # create an empty stack to store opening brackets
        for c in s: # loop through each character in the string
            if c in '([{': # if the character is an opening bracket
                stack.append(c) # push it onto the stack
            else: # if the character is a closing bracket
                if not stack or \
                    (c == ')' and stack[-1] != '(') or \
                    (c == '}' and stack[-1] != '{') or \
                    (c == ']' and stack[-1] != '['):
                    return False # the string is not valid, so return false
                stack.pop() # otherwise, pop the opening bracket from the stack
        return not stack # if the stack is empty, all opening brackets have been matched with their corresponding closing brackets,
                         # so the string is valid, otherwise, there are unmatched opening brackets, so return false
```

thankyou