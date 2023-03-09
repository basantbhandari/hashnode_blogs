---
title: "Reindexing in pandas?"
datePublished: Thu Mar 09 2023 08:13:20 GMT+0000 (Coordinated Universal Time)
cuid: clf0u0np1000009jn7glm9tij
slug: reindexing-in-pandas
tags: reindexing

---

Reindexing in pandas refers to the process of changing the row and/or column labels of a data frame or a Series. This can be useful when you want to align two or more data structures based on their labels, or when you want to add or remove rows or columns from a data frame or a Series.

In Pandas, you can reindex a DataFrame or a Series using the `reindex()` method. The `reindex()` the method takes one or more arguments, depending on whether you want to reindex the rows, the columns, or both.

Here's an example of reindexing a data frame:

```python
import pandas as pd

# create a DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'Salary': [50000, 60000, 70000, 80000]}
df = pd.DataFrame(data)

# reindex the DataFrame
df = df.reindex([3, 2, 1, 0])

print(df)
```

Output:

```python
 code       Name  Age  Salary
3     David   40   80000
2   Charlie   35   70000
1       Bob   30   60000
0     Alice   25   50000
```

In the above example, we created a data frame with four rows and three columns. We then reindexed the DataFrame by passing a new list of row labels to the `reindex()` method. This reversed the order of the rows in the data frame.

You can also reindex the columns of a DataFrame by passing a new list of column labels to the `reindex()` method:

```python
import pandas as pd

# create a DataFrame
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'Salary': [50000, 60000, 70000, 80000]}
df = pd.DataFrame(data)

# reindex the columns of the DataFrame
df = df.reindex(columns=['Name', 'Salary', 'Age'])

print(df)
```

Output:

```python
 code       Name  Salary  Age
0     Alice   50000   25
1       Bob   60000   30
2   Charlie   70000   35
3     David   80000   40
```

In the above example, we reindexed the columns of the DataFrame by passing a new list of column labels to the `reindex()` method. This changed the order of the columns in the data frame.

Reindexing can also be used to add or remove rows or columns from a DataFrame or a Series by passing a new list of labels to the `reindex()` method. If a label in the new list does not exist in the original data structure, Pandas will fill the corresponding row or column with `NaN` values.