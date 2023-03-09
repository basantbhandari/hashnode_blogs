---
title: "create a series from dict in Pandas?"
datePublished: Thu Mar 09 2023 08:35:03 GMT+0000 (Coordinated Universal Time)
cuid: clf0uskzp000q09mohqtl9qxk
slug: create-a-series-from-dict-in-pandas
tags: create-a-series-from-dict-in-pandas

---

You can create a Pandas Series from a dictionary by passing the dictionary to the `pd.Series()` function. The keys of the dictionary will become the index of the Series, and the values will become the data in the Series. Here is an example:

```python
import pandas as pd

data = {'a': 1, 'b': 2, 'c': 3}

s = pd.Series(data)

print(s)
```

Output:

```python
a    1
b    2
c    3
dtype: int64
```

In the example above, we created a dictionary `data` with keys 'a', 'b', and 'c' and corresponding values 1, 2, and 3. We then passed this dictionary to the `pd.Series()` function to create a Series `s`. The resulting Series has index labels 'a', 'b', and 'c' and corresponding values 1, 2, and 3.

You can also pass a list of keys to the `pd.Series()` function to specify the order of the index labels:

```python
import pandas as pd

data = {'a': 1, 'b': 2, 'c': 3}

s = pd.Series(data, index=['c', 'b', 'a'])

print(s)
```

Output:

```python
c    3
b    2
a    1
dtype: int64
```

In the example above, we passed the list \['c', 'b', 'a'\] as the `index` parameter to the `pd.Series()` function to specify the order of the index labels in the resulting Series.