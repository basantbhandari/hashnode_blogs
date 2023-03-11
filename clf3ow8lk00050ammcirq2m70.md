---
title: "Pandas NumPy array?"
datePublished: Sat Mar 11 2023 08:13:14 GMT+0000 (Coordinated Universal Time)
cuid: clf3ow8lk00050ammcirq2m70
slug: pandas-numpy-array
tags: pandas-numpy-array

---

In Pandas, you can convert a DataFrame or a Series into a NumPy array using the `values` attribute.

Here's an example of converting a DataFrame to a NumPy array:

```python
import pandas as pd
import numpy as np

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# Convert the DataFrame to a NumPy array
arr = df.values

print(arr)
print(type(arr))
```

Output:

```python
[[1 4]
 [2 5]
 [3 6]]
<class 'numpy.ndarray'>
```

As you can see, the DataFrame has been converted to a two-dimensional NumPy array.

You can also convert a Series to a one-dimensional NumPy array using the `values` attribute. Here's an example:

```python
import pandas as pd
import numpy as np

# Create a Series
s = pd.Series([1, 2, 3])

# Convert the Series to a NumPy array
arr = s.values

print(arr)
print(type(arr))
```

Output:

```python
[1 2 3]
<class 'numpy.ndarray'>
```

As you can see, the Series has been converted to a one-dimensional NumPy array.