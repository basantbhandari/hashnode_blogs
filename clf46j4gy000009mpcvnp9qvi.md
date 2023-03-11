---
title: "slicing in python"
datePublished: Sat Mar 11 2023 16:26:55 GMT+0000 (Coordinated Universal Time)
cuid: clf46j4gy000009mpcvnp9qvi
slug: slicing-in-python
tags: slicing-in-python

---

In Python, slicing is a technique for extracting a portion of a sequence (e.g., a list, tuple, or string) by specifying a start and end index. The general syntax for slicing is as follows:

```python
sequence[start:end:step]
```

* `start`: the starting index of the slice (inclusive). If omitted, the default value is 0.
    
* `end`: the ending index of the slice (exclusive). If omitted, the default value is the length of the sequence.
    
* `step`: the step size between elements. If omitted, the default value is 1.
    

Here are some examples of slicing:

```python
# slicing a list
my_list = [1, 2, 3, 4, 5]
print(my_list[1:3])   # [2, 3]
print(my_list[:3])    # [1, 2, 3]
print(my_list[::2])   # [1, 3, 5]

# slicing a string
my_string = "Hello, World!"
print(my_string[7:])   # "World!"
print(my_string[:5])   # "Hello"
print(my_string[::2])  # "Hlo ol!"
```

Note that slicing does not modify the original sequence; it returns a new sequence that contains the sliced elements.