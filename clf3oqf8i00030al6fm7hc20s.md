---
title: "sort the DataFrame in pandas"
datePublished: Sat Mar 11 2023 08:08:43 GMT+0000 (Coordinated Universal Time)
cuid: clf3oqf8i00030al6fm7hc20s
slug: sort-the-dataframe-in-pandas
tags: sort-the-dataframe-in-pandas

---

In Pandas, you can sort a data frame by one or more columns using the `sort_values()` method.

Here's an example of sorting a data frame by a single column:

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [3, 2, 1], 'B': [6, 5, 4]})

# Sort the DataFrame by column 'A'
df = df.sort_values('A')

print(df)
```

Output:

```python
   A  B
2  1  4
1  2  5
0  3  6
```

As you can see, the DataFrame has been sorted in ascending order by column 'A'.

You can also sort a data frame by multiple columns by passing a list of column names to the `sort_values()` method. Here's an example:

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [3, 2, 1], 'B': [6, 5, 4], 'C': [9, 8, 7]})

# Sort the DataFrame by columns 'A' and 'B'
df = df.sort_values(['A', 'B'])

print(df)
```

Output:

```python
   A  B  C
2  1  4  7
1  2  5  8
0  3  6  9
```

As you can see, the DataFrame has been sorted first by column 'A' and then by column 'B'.

By default, `sort_values()` sorts the DataFrame in ascending order. However, you can sort in descending order by passing `ascending=False` as an argument to the method. Here's an example:

```python
import pandas as pd

# Create a DataFrame
df = pd.DataFrame({'A': [3, 2, 1], 'B': [6, 5, 4], 'C': [9, 8, 7]})

# Sort the DataFrame by column 'A' in descending order
df = df.sort_values('A', ascending=False)

print(df)
```

Output:

```python
   A  B  C
0  3  6  9
1  2  5  8
2  1  4  7
```

As you can see, the DataFrame has been sorted in descending order by column 'A'.