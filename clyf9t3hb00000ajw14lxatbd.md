---
title: "79. Word Search"
datePublished: Wed Jul 10 2024 03:18:32 GMT+0000 (Coordinated Universal Time)
cuid: clyf9t3hb00000ajw14lxatbd
slug: 79-word-search
tags: dsa

---

Given an `m x n` grid of characters `board` and a string `word`, return `true` *if* `word` *exists in the grid*.

The word can be constructed from letters of sequentially adjacent cells, where adjacent cells are horizontally or vertically neighboring. The same letter cell may not be used more than once.

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720532573463/78418342-6e89-47f5-80ef-250469fd385a.jpeg align="center")

```python
Input: board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "ABCCED"
Output: true
```

**Example 2:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720532590256/f3513e31-8827-4385-97e7-11c3df33e699.jpeg align="center")

```python
Input: board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "SEE"
Output: true
```

**Example 3:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720532616022/1b6ad5a6-91d4-4285-90cc-b90e9db6895e.jpeg align="center")

```python
Input: board = [["A","B","C","E"],["S","F","C","S"],["A","D","E","E"]], word = "ABCB"
Output: false
```

**Constraints:**

* `m == board.length`
    
* `n = board[i].length`
    
* `1 <= m, n <= 6`
    
* `1 <= word.length <= 15`
    
* `board` and `word` consists of only lowercase and uppercase English letters.
    

**Solution:**

```python
class Solution:
    
    def exist(self, board: List[List[str]], word: str) -> bool:
        m = len(board)
        n = len(board[0])
        
        for i in range(m):
            for j in range(n):
                if board[i][j] == word[0]:
                    if self.dfs(board, word, 0, i, j, m, n):
                        return True
        
        return False
    
    def dfs(self, board: List[List[str]], word: str, index: int, i: int, j: int, m: int, n: int):
        if i < 0 or i >= m or j < 0 or j >= n or board[i][j] != word[index]:
            return False
        if index == len(word) - 1:
            return True
        
        board[i][j] = '#'
        
        if (self.dfs(board, word, index + 1, i - 1, j, m, n)
            or self.dfs(board, word, index + 1, i + 1, j, m, n)
            or self.dfs(board, word, index + 1, i, j - 1, m, n)
            or self.dfs(board, word, index + 1, i, j + 1, m, n)):
            return True
        
        board[i][j] = word[index]
        return False
```