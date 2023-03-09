---
title: "Series in Pandas?"
datePublished: Thu Mar 09 2023 07:57:50 GMT+0000 (Coordinated Universal Time)
cuid: clf0tgqmk000b09mobkr74wo5
slug: series-in-pandas
tags: series, series-in-pandas

---

A Series in Pandas is a one-dimensional labeled array that can hold any data type such as integers, floats, strings, or Python objects. The Series has two main components: the index and the data. The index is a unique label for each element in the Series, and the data can be a NumPy array or a Python object.

A Series can be created using the `pd.Series()` function and you can pass either a NumPy array, a Python list, or a dictionary as input. If you pass a dictionary as input, the keys of the dictionary will become the index labels for the Series, and the values of the dictionary will become the data.

Example:

```python
import pandas as pd
import numpy as np

# create a Series from a list of integers
data = [1, 3, 5, np.nan, 6, 8]
s = pd.Series(data)
print(s)
```

Output:

```python
0    1.0
1    3.0
2    5.0
3    NaN
4    6.0
5    8.0
dtype: float64
```

In the above example, we created a series from a list of integers, and one of the values is `NaN` (not a number), which represents missing or undefined data.

You can also specify custom index labels when creating a Series using the `index` parameter:

```python
import pandas as pd
import numpy as np

# create a Series from a dictionary with custom index labels
data = {'a': 0., 'b': 1., 'c': 2.}
s = pd.Series(data, index=['b', 'c', 'd', 'a'])
print(s)
```

Output:

```python
b    1.0
c    2.0
d    NaN
a    0.0
dtype: float64
```

In the above example, we created a series from a dictionary with custom index labels, and one of the index labels (`d`) does not exist in the dictionary, so it is assigned a `NaN` value.