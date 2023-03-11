---
title: "convert a numpy array to a data frame of a given shape?"
datePublished: Sat Mar 11 2023 08:20:38 GMT+0000 (Coordinated Universal Time)
cuid: clf3p5ram000509ms9udjd5p6
slug: convert-a-numpy-array-to-a-data-frame-of-a-given-shape
tags: convert-a-numpy-array-to-a-data-frame-of-a-given-shape

---

In Pandas, you can convert a NumPy array to a DataFrame of a given shape using the `reshape()` method.

Here's an example of converting a NumPy array to a DataFrame of a given shape:

```python
import pandas as pd
import numpy as np

# Create a NumPy array
arr = np.array([1, 2, 3, 4, 5, 6])

# Reshape the array to a two-dimensional array
arr_reshaped = arr.reshape(2, 3)

# Convert the array to a DataFrame
df = pd.DataFrame(arr_reshaped)

print(df)
```

Output:

```python
   0  1  2
0  1  2  3
1  4  5  6
```

As you can see, the NumPy array has been reshaped to a two-dimensional array with the shape of `(2, 3)` and then converted to a data frame.

You can also set custom column names and index labels when creating the DataFrame by passing them as arguments to the `pd.DataFrame()` method. Here's an example:

```python
import pandas as pd
import numpy as np

# Create a NumPy array
arr = np.array([1, 2, 3, 4, 5, 6])

# Reshape the array to a two-dimensional array
arr_reshaped = arr.reshape(2, 3)

# Convert the array to a DataFrame with custom column names and index labels
df = pd.DataFrame(arr_reshaped, columns=['A', 'B', 'C'], index=['X', 'Y'])

print(df)
```

Output:

```python
   A  B  C
X  1  2  3
Y  4  5  6
```

As you can see, the DataFrame now has custom column names and index labels.