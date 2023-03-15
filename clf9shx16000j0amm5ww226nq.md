---
title: "Python Arrays"
datePublished: Wed Mar 15 2023 14:40:41 GMT+0000 (Coordinated Universal Time)
cuid: clf9shx16000j0amm5ww226nq
slug: python-arrays
tags: python-arrays

---

there are several ways to represent arrays, which are also called sequences. Here are some common types of arrays/sequences in Python:

1. Lists: Lists are one of the most versatile and commonly used sequences in Python. A list is a collection of values, which can be of any type. Lists are created using square brackets `[ ]` and individual items are separated by commas. For example:
    

```python
my_list = [1, 2, 3, 'four', 'five']
```

1. Tuples: Tuples are similar to lists, but they are immutable, meaning that once they are created, their contents cannot be changed. Tuples are created using parentheses `( )` and individual items are separated by commas. For example:
    

```python
my_tuple = (1, 2, 3, 'four', 'five')
```

1. Arrays: Arrays are used to store homogeneous data, meaning all elements in the array must be of the same data type. Arrays can be created using the `array` module in Python. For example:
    

```python
import array
my_array = array.array('i', [1, 2, 3, 4, 5])
```

Here, `'i'` specifies the type of the elements in the array, which is `int` in this case.

1. NumPy arrays: NumPy is a powerful library for numerical computing in Python. NumPy arrays are similar to arrays, but they can store multidimensional data and support many mathematical operations. NumPy arrays are created using the `numpy` module. For example:
    

```python
import numpy as np
my_np_array = np.array([[1, 2], [3, 4]])
```

Here, `[[1, 2], [3, 4]]` is a 2-dimensional array.

These are some common types of arrays/sequences in Python. Depending on the requirements of your program, you may choose to use one or more of these types of arrays.