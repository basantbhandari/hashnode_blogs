---
title: "Valid Sudoku"
datePublished: Sat Jul 06 2024 14:24:41 GMT+0000 (Coordinated Universal Time)
cuid: clya7udeu000209iecmb2ehld
slug: valid-sudoku
tags: dsa

---

Determine if a `9 x 9` Sudoku board is valid. Only the filled cells need to be validated **according to the following rules**:

1. Each row must contain the digits `1-9` without repetition.
    
2. Each column must contain the digits `1-9` without repetition.
    
3. Each of the nine `3 x 3` sub-boxes of the grid must contain the digits `1-9` without repetition.
    

**Note:**

* A Sudoku board (partially filled) could be valid but is not necessarily solvable.
    
* Only the filled cells need to be validated according to the mentioned rules.
    

**Example 1:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1720274943278/20e98096-0ca1-4837-91d3-a028973779f5.png align="center")

```python
Input: board = 
[["5","3",".",".","7",".",".",".","."]
,["6",".",".","1","9","5",".",".","."]
,[".","9","8",".",".",".",".","6","."]
,["8",".",".",".","6",".",".",".","3"]
,["4",".",".","8",".","3",".",".","1"]
,["7",".",".",".","2",".",".",".","6"]
,[".","6",".",".",".",".","2","8","."]
,[".",".",".","4","1","9",".",".","5"]
,[".",".",".",".","8",".",".","7","9"]]
Output: true
```

**Example 2:**

```python
Input: board = 
[["8","3",".",".","7",".",".",".","."]
,["6",".",".","1","9","5",".",".","."]
,[".","9","8",".",".",".",".","6","."]
,["8",".",".",".","6",".",".",".","3"]
,["4",".",".","8",".","3",".",".","1"]
,["7",".",".",".","2",".",".",".","6"]
,[".","6",".",".",".",".","2","8","."]
,[".",".",".","4","1","9",".",".","5"]
,[".",".",".",".","8",".",".","7","9"]]
Output: false
Explanation: Same as Example 1, except with the 5 in the top left corner being modified to 8. Since there are two 8's in the top left 3x3 sub-box, it is invalid.
```

**Constraints:**

* `board.length == 9`
    
* `board[i].length == 9`
    
* `board[i][j]` is a digit `1-9` or `'.'`.
    

Solution:

```python
class Solution:
    def isValidSudoku(self, board: List[List[str]]) -> bool:
        cols = defaultdict(set)
        rows = defaultdict(set)
        squares = defaultdict(set)  # key = (r /3, c /3)

        for r in range(9):
            for c in range(9):
                # if there is space
                if board[r][c] == ".":
                    continue
                # if duplicate in rows, cols and square
                if (
                    board[r][c] in rows[r]
                    or board[r][c] in cols[c]
                    or board[r][c] in squares[(r // 3, c // 3)]
                ):
                    return False
                
                # update the hash set
                cols[c].add(board[r][c])
                rows[r].add(board[r][c])
                squares[(r // 3, c // 3)].add(board[r][c])

        return True
```