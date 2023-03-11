---
title: "convert a Series to DataFrame in pandas?"
datePublished: Sat Mar 11 2023 08:16:51 GMT+0000 (Coordinated Universal Time)
cuid: clf3p0w5c000009mp3xw37hzo
slug: convert-a-series-to-dataframe-in-pandas
tags: convert-a-series-to-dataframe-in-pandas

---

In Pandas, you can convert a Series to a data frame using the `to_frame()` method.

Here's an example of converting a Series to a data frame:

```python
import pandas as pd

# Create a Series
s = pd.Series([1, 2, 3])

# Convert the Series to a DataFrame
df = s.to_frame()

print(df)
```

Output:

```python
   0
0  1
1  2
2  3
```

As you can see, the Series has been converted to a one-column data frame. By default, the column name is set to `0`. You can set a custom column name by passing it as an argument to the `to_frame()` method. Here's an example:

```python
import pandas as pd

# Create a Series
s = pd.Series([1, 2, 3])

# Convert the Series to a DataFrame with a custom column name
df = s.to_frame('my_column')

print(df)
```

Output:

```python
   my_column
0          1
1          2
2          3
```

As you can see, the DataFrame now has a custom column name.