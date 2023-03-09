---
title: "Categorical data in Pandas?"
datePublished: Thu Mar 09 2023 08:30:06 GMT+0000 (Coordinated Universal Time)
cuid: clf0um87n000a09mdd3uy2ya6
slug: categorical-data-in-pandas
tags: categorical-data-in-pandas

---

Categorical data in Pandas is a data type used to represent data that has a limited number of possible values. This data type is useful for working with data that has a small number of distinct values, such as the categories in a survey response or the classification of a product.

In Pandas, the `Categorical` data type is represented by the `Categorical` class. You can create an `Categorical` object by calling the `pd.Categorical()` function on a list or array of data. For example:

```python
import pandas as pd

data = ['cat', 'dog', 'dog', 'cat', 'bird']

cat = pd.Categorical(data)
print(cat)
```

Output:

```python
['cat', 'dog', 'dog', 'cat', 'bird']
Categories (3, object): ['bird', 'cat', 'dog']
```

In the example above, we created a `Categorical` object from a list of animal names. The `Categorical` object has three possible categories: 'bird', 'cat', and 'dog'. You can access the categories using the `.categories` attribute of the `Categorical` object:

```python
print(cat.categories)
```

Output:

```python
Index(['bird', 'cat', 'dog'], dtype='object')
```

You can also convert a column in a DataFrame to a `Categorical` data type using the `.astype()` method:

```python
import pandas as pd

df = pd.DataFrame({'animal': ['cat', 'dog', 'dog', 'cat', 'bird']})

df['animal'] = df['animal'].astype('category')
print(df['animal'])
```

Output:

```python
0     cat
1     dog
2     dog
3     cat
4    bird
Name: animal, dtype: category
Categories (3, object): ['bird', 'cat', 'dog']
```

Once a column is converted to a `Categorical` data type, you can use methods like `.value_counts()` to get a count of each category:

```python
print(df['animal'].value_counts())
```

Output:

```python
cat     2
dog     2
bird    1
Name: animal, dtype: int64
```

Categorical data in Pandas is useful for working with data that has a small number of distinct values and can be an efficient way to store and manipulate data in memory.