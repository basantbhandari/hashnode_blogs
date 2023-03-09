---
title: "How to Delete Indices, Rows, or Columns From a Pandas Data Frame?"
datePublished: Thu Mar 09 2023 10:22:54 GMT+0000 (Coordinated Universal Time)
cuid: clf0yn9yu00080ajvgt9ncjt5
slug: how-to-delete-indices-rows-or-columns-from-a-pandas-data-frame
tags: delete-indices-rows-or-columns-from-a-pandas-data-frame

---

To delete indices, rows, or columns from a Pandas DataFrame, you can use the `drop` method. Here are some examples:

1. Delete a column:
    

To delete a column, you can use the `drop` method with the `columns` the argument set to the label of the column to be deleted, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28], 'Gender': ['Male', 'Male', 'Female']})
df = df.drop('Gender', axis=1)
print(df)
```

Output:

```python
    Name  Age
0   John   25
1   Mike   32
2  Sarah   28
```

1. Delete a row:
    

To delete a row, you can use the `drop` method with the `index` the argument set to the label of the row to be deleted, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})
df = df.drop(1, axis=0)
print(df)
```

Output:

```python
    Name  Age
0   John   25
2  Sarah   28
```

1. Delete multiple rows or columns:
    

You can delete multiple rows or columns by passing a list of labels to the `drop` method. For example, to delete the second and third rows of the DataFrame, you can do this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})
df = df.drop([1, 2], axis=0)
print(df)
```

Output:

```python
   Name  Age
0  John   25
```

In each example, we use the `drop` method to remove the specified rows or columns from the data frame. The `axis` parameter specifies whether to remove rows (`axis=0`) or columns (`axis=1`). The resulting DataFrame is assigned back to the original variable to modify the data frame in place.