---
title: "150. Evaluate Reverse Polish Notation"
datePublished: Sun Jul 07 2024 03:53:14 GMT+0000 (Coordinated Universal Time)
cuid: clyb0q6li00040al6bzpfa41y
slug: 150-evaluate-reverse-polish-notation
tags: dsa

---

You are given an array of strings `tokens` that represents an arithmetic expression in a [Reverse Polish Notation](http://en.wikipedia.org/wiki/Reverse_Polish_notation).

Evaluate the expression. Return *an integer that represents the value of the expression*.

**Note** that:

* The valid operators are `'+'`, `'-'`, `'*'`, and `'/'`.
    
* Each operand may be an integer or another expression.
    
* The division between two integers always **truncates toward zero**.
    
* There will not be any division by zero.
    
* The input represents a valid arithmetic expression in a reverse polish notation.
    
* The answer and all the intermediate calculations can be represented in a **32-bit** integer.
    

**Example 1:**

```python
Input: tokens = ["2","1","+","3","*"]
Output: 9
Explanation: ((2 + 1) * 3) = 9
```

**Example 2:**

```python
Input: tokens = ["4","13","5","/","+"]
Output: 6
Explanation: (4 + (13 / 5)) = 6
```

**Example 3:**

```python
Input: tokens = ["10","6","9","3","+","-11","*","/","*","17","+","5","+"]
Output: 22
Explanation: ((10 * (6 / ((9 + 3) * -11))) + 17) + 5
= ((10 * (6 / (12 * -11))) + 17) + 5
= ((10 * (6 / -132)) + 17) + 5
= ((10 * 0) + 17) + 5
= (0 + 17) + 5
= 17 + 5
= 22
```

**Constraints:**

* `1 <= tokens.length <= 10<sup>4</sup>`
    
* `tokens[i]` is either an operator: `"+"`, `"-"`, `"*"`, or `"/"`, or an integer in the range `[-200, 200]`.
    

Solution:

```python
class Solution:
    def evalRPN(self, tokens: List[str]) -> int:
        stack = []
        for c in tokens:
            if c == "+":
                stack.append(stack.pop() + stack.pop())
            elif c == "-":
                a, b = stack.pop(), stack.pop()
                stack.append(b - a)
            elif c == "*":
                stack.append(stack.pop() * stack.pop())
            elif c == "/":
                a, b = stack.pop(), stack.pop()
                stack.append(int(float(b) / a))
            else:
                stack.append(int(c))
        return stack[0]
```