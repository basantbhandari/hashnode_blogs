---
title: "create a copy of the series in Pandas?"
datePublished: Thu Mar 09 2023 08:39:17 GMT+0000 (Coordinated Universal Time)
cuid: clf0uy17d000b0amn8a7o0w2j
slug: create-a-copy-of-the-series-in-pandas
tags: a-copy-of-the-series-in-pandas, create-a-copy-of-the-series-in-pandas

---

To create a copy of a Pandas Series, you can use the `.copy()` method. The `.copy()` the method creates a new Series that is a copy of the original Series, with the same data and index labels. Here is an example:

```python
import pandas as pd

s = pd.Series([1, 2, 3])

s_copy = s.copy()

print(s_copy)
```

Output:

```python
0    1
1    2
2    3
dtype: int64
```

In the example above, we created a series `s` with values 1, 2, and 3. We then created a copy of `s` using the `.copy()` method and assigned it to `s_copy`. The resulting Series `s_copy` has the same data and index labels as the original Series `s`.

Note that it is important to create a copy of a Series if you want to modify the data in the Series without affecting the original Series. If you modify a Series without creating a copy, the original Series will also be modified. For example:

```python
import pandas as pd

s = pd.Series([1, 2, 3])

s_copy = s

s_copy[0] = 4

print(s)
```

Output:

```python
0    4
1    2
2    3
dtype: int64
```

In the example above, we assigned `s` to `s_copy` without creating a copy using the `.copy()` method. We then modified the first element of `s_copy`. The resulting Series `s` is also modified because `s_copy` and `s` reference the same underlying data.