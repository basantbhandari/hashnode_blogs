---
title: "get frequency counts of unique items of a series in pandas."
datePublished: Sat Mar 11 2023 08:23:28 GMT+0000 (Coordinated Universal Time)
cuid: clf3p9e2z000b0amm7msz8bh7
slug: get-frequency-counts-of-unique-items-of-a-series-in-pandas
tags: get-frequency-counts-of-unique-items-of-a-series-in-pandas

---

In Pandas, you can get the frequency counts of unique items of a Series using the `value_counts()` method.

Here's an example of getting the frequency counts of unique items of a Series:

```python
import pandas as pd

# Create a Series
s = pd.Series(['A', 'B', 'A', 'C', 'B', 'A'])

# Get the frequency counts of unique items in the Series
counts = s.value_counts()

print(counts)
```

Output:

```python
A    3
B    2
C    1
dtype: int64
```

As you can see, the `value_counts()` the method has returned a new Series with the unique items in the original Series as the index and their frequency counts as the values.

You can also normalize the frequency counts to get the proportion of each unique item in the Series by passing the argument `normalize=True` to the `value_counts()` method. Here's an example:

```python
import pandas as pd

# Create a Series
s = pd.Series(['A', 'B', 'A', 'C', 'B', 'A'])

# Get the normalized frequency counts of unique items in the Series
counts = s.value_counts(normalize=True)

print(counts)
```

Output:

```python
A    0.500000
B    0.333333
C    0.166667
dtype: float64
```

As you can see, the frequency counts have been normalized to proportions between 0 and 1.