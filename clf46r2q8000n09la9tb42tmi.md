---
title: "break, continue, and pass in Python?"
datePublished: Sat Mar 11 2023 16:33:06 GMT+0000 (Coordinated Universal Time)
cuid: clf46r2q8000n09la9tb42tmi
slug: break-continue-and-pass-in-python
tags: break-continue-and-pass-in-python

---

In Python, `break`, `continue`, and `pass` are control flow statements that can be used to modify the behavior of loops and conditional statements.

* `break` is used to exit a loop prematurely. When `break` is encountered inside a loop, the loop is immediately terminated and program control is transferred to the next statement after the loop. Here's an example:
    

```python
for i in range(10):
    if i == 5:
        break
    print(i)
# Output: 0 1 2 3 4
```

In this example, the loop exits when `i` is equal to 5, and the remaining iterations are skipped.

* `continue` is used to skip the current iteration of a loop and move on to the next one. When `continue` is encountered inside a loop, the remaining statements in the loop are skipped and program control is transferred to the next iteration of the loop. Here's an example:
    

```python
for i in range(10):
    if i == 5:
        continue
    print(i)
# Output: 0 1 2 3 4 6 7 8 9
```

In this example, the iteration for `i=5` is skipped and the loop continues with the next iteration.

* `pass` is a null operation that does nothing. It can be used as a placeholder when a statement is required syntactically, but no action is required. Here's an example:
    

```python
def my_function():
    pass
```

In this example, `pass` is used to define an empty function that does nothing.

In summary, `break` and `continue` are used to modify the behavior of loops, while `pass` is used to define a placeholder statement that does nothing.