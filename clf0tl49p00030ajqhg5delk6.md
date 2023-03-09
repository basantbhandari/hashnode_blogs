---
title: "calculate the standard deviation from the Series? in pandas"
datePublished: Thu Mar 09 2023 08:01:15 GMT+0000 (Coordinated Universal Time)
cuid: clf0tl49p00030ajqhg5delk6
slug: calculate-the-standard-deviation-from-the-series-in-pandas
tags: calculate-the-standard-deviation-from-the-series

---

You can calculate the standard deviation from a Series in Pandas using the `std()` function. The `std()` the function returns the standard deviation of the non-null values in the Series.

Example:

```python
import pandas as pd

# create a Series
s = pd.Series([2, 4, 6, 8, 10])

# calculate the standard deviation
std = s.std()

print("Standard deviation:", std)
```

Output:

```python
Standard deviation: 2.8284271247461903
```

In the above example, we created a Series with five integer values, and we calculated the standard deviation using the `std()` function. The standard deviation of the values in the Series is 2.8284. If the Series contains any null or missing values, the `std()` the function will return NaN.