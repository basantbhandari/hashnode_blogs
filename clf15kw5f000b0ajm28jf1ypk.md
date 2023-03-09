---
title: "iterate over a Pandas DataFrame?"
datePublished: Thu Mar 09 2023 13:37:00 GMT+0000 (Coordinated Universal Time)
cuid: clf15kw5f000b0ajm28jf1ypk
slug: iterate-over-a-pandas-dataframe
tags: iterate-over-a-pandas-dataframe

---

There are different ways to iterate over a Pandas data frame. However, it is important to keep in mind that Pandas is optimized for vectorized operations and it is generally recommended to avoid iterating over a data frame as much as possible.

Here are some common ways to iterate over a Pandas data frame:

1. `iterrows()` method: This method returns an iterator that yields pairs of index and row data as pandas Series objects. It is useful when you need to access each row individually.
    

```python
import pandas as pd

# create a sample DataFrame
df = pd.DataFrame({'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 35]})

# iterate over the rows
for index, row in df.iterrows():
    print(index, row['name'], row['age'])
```

Output:

```python
0 Alice 25
1 Bob 30
2 Charlie 35
```

1. `itertuples()` method: This method returns an iterator that yields named tuples of the rows in the DataFrame. It is faster than `iterrows()` as it returns tuples and avoids the overhead of constructing a Series object for each row.
    

```python
import pandas as pd

# create a sample DataFrame
df = pd.DataFrame({'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 35]})

# iterate over the rows
for row in df.itertuples():
    print(row.Index, row.name, row.age)
```

Output:

```python
0 Alice 25
1 Bob 30
2 Charlie 35
```

1. Vectorized operations: As mentioned earlier, Pandas is optimized for vectorized operations, which means you can often perform operations on entire columns or subsets of columns without needing to iterate over each row. For example, you can use the `apply()` method to apply a function to each column or row of a data frame.
    

```python
import pandas as pd

# create a sample DataFrame
df = pd.DataFrame({'name': ['Alice', 'Bob', 'Charlie'], 'age': [25, 30, 35]})

# apply a function to each column
df.apply(lambda x: x.max())

# apply a function to each row
df.apply(lambda x: x['name'] + ' is ' + str(x['age']), axis=1)
```

Output:

```python
name    Charlie
age           35
dtype: object

0      Alice is 25
1         Bob is 30
2    Charlie is 35
dtype: object
```