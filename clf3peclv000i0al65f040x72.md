---
title: "get the minimum, 25th percentile, median, 75th, and max of a numeric series?"
datePublished: Sat Mar 11 2023 08:27:19 GMT+0000 (Coordinated Universal Time)
cuid: clf3peclv000i0al65f040x72
slug: get-the-minimum-25th-percentile-median-75th-and-max-of-a-numeric-series
tags: get-the-minimum-25th-percentile-median-75th-and-max-of-a-numeric-series

---

In Pandas, you can use the `describe()` method to get summary statistics, including the minimum, 25th percentile, median, 75th percentile, and maximum, of a numeric Series.

Here's an example of using the `describe()` method to get summary statistics of a numeric Series:

```python
import pandas as pd

# Create a numeric Series
s = pd.Series([10, 20, 30, 40, 50])

# Get the summary statistics of the Series
stats = s.describe()

print(stats)
```

Output:

```python
count     5.000000
mean     30.000000
std      15.811388
min      10.000000
25%      20.000000
50%      30.000000
75%      40.000000
max      50.000000
dtype: float64
```

As you can see, the `describe()` the method has returned a new Series with the summary statistics of the original Series.

You can also use individual methods to get specific summary statistics of a numeric Series. Here's an example:

```python
import pandas as pd

# Create a numeric Series
s = pd.Series([10, 20, 30, 40, 50])

# Get the minimum, 25th percentile, median, 75th percentile, and maximum of the Series
min_val = s.min()
q1 = s.quantile(0.25)
median = s.median()
q3 = s.quantile(0.75)
max_val = s.max()

print('Minimum:', min_val)
print('25th percentile:', q1)
print('Median:', median)
print('75th percentile:', q3)
print('Maximum:', max_val)
```

Output:

```python
Minimum: 10
25th percentile: 20.0
Median: 30.0
75th percentile: 40.0
Maximum: 50
```

As you can see, we have used the `min()`, `quantile()`, `median()`, and `max()` methods to get specific summary statistics of the original Series.