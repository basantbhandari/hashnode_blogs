---
title: "add an Index, row, or column to a Pandas DataFrame?"
datePublished: Thu Mar 09 2023 09:58:38 GMT+0000 (Coordinated Universal Time)
cuid: clf0xs2jq000209jx3rr43dqr
slug: add-an-index-row-or-column-to-a-pandas-dataframe
tags: add-an-index-row-or-column-to-a-pandas-dataframe

---

To add an index, row, or column to a Pandas DataFrame, you can use any of the following approaches:

1. Adding an index:
    

You can add an index to a Pandas DataFrame by assigning a list of labels to the `index` property of the DataFrame, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})
df.index = ['A', 'B', 'C']
print(df)
```

Output:

```python
    Name  Age
A   John   25
B   Mike   32
C  Sarah   28
```

1. Adding a row:
    

You can add a row to a Pandas DataFrame by appending a new row as a dictionary to the DataFrame, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})
new_row = {'Name': 'Tom', 'Age': 30}
df = df.append(new_row, ignore_index=True)
print(df)
```

Output:

```python
    Name  Age
0   John   25
1   Mike   32
2  Sarah   28
3    Tom   30
```

1. Adding a column:
    

You can add a column to a Pandas DataFrame by assigning a list of values to a new column label, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})
df['Gender'] = ['Male', 'Male', 'Female']
print(df)
```

Output:

```python
    Name  Age  Gender
0   John   25    Male
1   Mike   32    Male
2  Sarah   28  Female
```

In each of the above examples, we modify the DataFrame by assigning a new value to the `index`, `columns`, or adding a new row as a dictionary. Note that appending a row to a DataFrame returns a new DataFrame, so it is necessary to assign the result back to the original variable to modify the DataFrame in place.