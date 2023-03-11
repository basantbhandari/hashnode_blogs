---
title: "Reset the index in pandas?"
datePublished: Sat Mar 11 2023 08:05:14 GMT+0000 (Coordinated Universal Time)
cuid: clf3oly9a000r09lgb07b1mfz
slug: reset-the-index-in-pandas
tags: reset-the-index-in-pandas

---

In Pandas, the `reset_index()` the method is used to reset the index of a data frame or a Series.

When you reset the index of a DataFrame, a new index is created with a default integer index starting from 0. The old index is added to the DataFrame as a new column.

Here's an example:

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [1, 2, 3], 'B': [4, 5, 6]}, index=['X', 'Y', 'Z'])

# Reset the index
df = df.reset_index()

print(df)
```

Output:

```python
  index  A  B
0     X  1  4
1     Y  2  5
2     Z  3  6
```

As you can see, the old index `X`, `Y`, and `Z` have been reset and a new integer index has been created. The old index has been added as a new column named "index".

You can also use the `reset_index()` method to reset the index of a Series. Here's an example:

```python
import pandas as pd

# Create a Series
s = pd.Series([1, 2, 3], index=['X', 'Y', 'Z'])

# Reset the index
s = s.reset_index()

print(s)
```

Output:

```python
  index  0
0     X  1
1     Y  2
2     Z  3
```

As you can see, the old index `X`, `Y`, and `Z` have been reset and a new integer index has been created. The values of the Series have been added as a new column named "0".