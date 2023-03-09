---
title: "DataFrame in Pandas?"
datePublished: Thu Mar 09 2023 08:05:37 GMT+0000 (Coordinated Universal Time)
cuid: clf0tqq9k000b09lcde7q87nj
slug: dataframe-in-pandas
tags: dataframe-in-pandas

---

A DataFrame in Pandas is a two-dimensional labeled data structure that can hold data of different types, including numerical, categorical, and text data. It is similar to a table in a relational database or a spreadsheet in Excel, where each row represents a record and each column represents a feature or attribute of the data.

A data frame can be created using the `pd.DataFrame()` function and you can pass a variety of data structures as input, such as a NumPy array, a Python list of lists, a dictionary of arrays or lists, or another DataFrame. The columns in a data frame can have different data types, such as integers, floats, strings, or even custom data types.

Example:

```python
import pandas as pd

# create a DataFrame from a dictionary of lists
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'Salary': [50000, 60000, 70000, 80000]}
df = pd.DataFrame(data)
print(df)
```

Output:

```python
    code       Name  Age  Salary
0     Alice   25   50000
1       Bob   30   60000
2   Charlie   35   70000
3     David   40   80000
```

In the above example, we created a data frame from a dictionary of lists, where each key in the dictionary corresponds to a column name in the data frame, and each value in the dictionary corresponds to the data in the column.

You can also specify custom index labels when creating a data frame using the `index` parameter:

```python
import pandas as pd

# create a DataFrame from a list of dictionaries with custom index labels
data = [{'Name': 'Alice', 'Age': 25, 'Salary': 50000},
        {'Name': 'Bob', 'Age': 30, 'Salary': 60000},
        {'Name': 'Charlie', 'Age': 35, 'Salary': 70000},
        {'Name': 'David', 'Age': 40, 'Salary': 80000}]
df = pd.DataFrame(data, index=['A', 'B', 'C', 'D'])
print(df)
```

Output:

```python
      Name  Age  Salary
A    Alice   25   50000
B      Bob   30   60000
C  Charlie   35   70000
D    David   40   80000
```

In the above example, we created a data frame from a list of dictionaries with custom index labels using the `index` parameter. The index labels are specified as a list of strings with the same length as the number of rows in the DataFrame.