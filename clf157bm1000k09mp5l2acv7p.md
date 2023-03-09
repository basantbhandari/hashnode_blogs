---
title: "Rename the Index or Columns of a Pandas DataFrame."
datePublished: Thu Mar 09 2023 13:26:26 GMT+0000 (Coordinated Universal Time)
cuid: clf157bm1000k09mp5l2acv7p
slug: rename-the-index-or-columns-of-a-pandas-dataframe
tags: rename-the-index-or-columns-of-a-pandas-dataframe

---

To rename the index or columns of a Pandas DataFrame, you can use the `rename` method. The `rename` the method returns a new DataFrame with the updated index or column names.

To rename the columns of a DataFrame, you can pass a dictionary with the current column names as keys and the new column names as values to the `rename` method's `columns` parameter:

```python
import pandas as pd

# create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# rename the columns
df = df.rename(columns={'A': 'newA', 'B': 'newB'})
```

To rename the index of a data frame, you can pass a dictionary with the current index values as keys and the new index values as values to the `rename` method's `index` parameter:

```python
# create a DataFrame with a default integer index
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# rename the index
df = df.rename(index={0: 'newIndex0', 1: 'newIndex1', 2: 'newIndex2'})
```

Alternatively, you can use the `set_axis` method to rename both the index and columns in one step:

```python
# create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]})

# rename the index and columns
df = df.set_axis(['newIndex0', 'newIndex1', 'newIndex2'], axis=0)
df = df.set_axis(['newA', 'newB'], axis=1)
```

Note that the `set_axis` the method returns a new DataFrame with the updated index and columns.