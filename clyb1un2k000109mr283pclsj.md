---
title: "22. Generate Parentheses"
datePublished: Sun Jul 07 2024 04:24:42 GMT+0000 (Coordinated Universal Time)
cuid: clyb1un2k000109mr283pclsj
slug: 22-generate-parentheses
tags: dsa

---

Given `n` pairs of parentheses, write a function to *generate all combinations of well-formed parentheses*.

**Example 1:**

```python
Input: n = 3
Output: ["((()))","(()())","(())()","()(())","()()()"]
```

**Example 2:**

```python
Input: n = 1
Output: ["()"]
```

**Constraints:**

* `1 <= n <= 8`
    

Solution:

```python
class Solution:
    def generateParenthesis(self, n: int) -> List[str]:
        """
        solving using backtracking kind of brute forcing
        only add open paranthesis if open < n
        only add a closing parenthesis if closed < open
        valid IIF open == closed == n
        """
        stack = []
        res = []

        def backtrack(openN, closedN):
            if openN == closedN == n:
                res.append("".join(stack))
                return None

            if openN < n:
                stack.append("(")
                backtrack(openN + 1, closedN)
                stack.pop()

            if closedN < openN:
                stack.append(")")
                backtrack(openN, closedN + 1)
                stack.pop()

        backtrack(0, 0)
        return res
```