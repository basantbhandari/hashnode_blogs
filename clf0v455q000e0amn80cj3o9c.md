---
title: "create an empty DataFrame in Pandas?"
datePublished: Thu Mar 09 2023 08:44:02 GMT+0000 (Coordinated Universal Time)
cuid: clf0v455q000e0amn80cj3o9c
slug: create-an-empty-dataframe-in-pandas
tags: create-an-empty-dataframe-in-pandas

---

To create an empty DataFrame in Pandas, you can use the `pd.DataFrame()` function and pass an empty dictionary, a list, or a numpy array as data. Here are examples of each approach:

```python
import pandas as pd

# Using an empty dictionary
df1 = pd.DataFrame({})

print(df1)
```

Output:

```python
Empty DataFrame
Columns: []
Index: []
```

```python
import pandas as pd

# Using an empty list
df2 = pd.DataFrame([])

print(df2)
```

Output:

```python
Empty DataFrame
Columns: []
Index: []
```

```python
pythonCopy codeimport pandas as pd
import numpy as np

# Using an empty numpy array
df3 = pd.DataFrame(np.array([]))

print(df3)
```

Output:

```python
Empty DataFrame
Columns: []
Index: []
```

In all three examples, we create an empty DataFrame with no columns or rows. This can be useful as a starting point for creating a data frame that you will populate with data later.