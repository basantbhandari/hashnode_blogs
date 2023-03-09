---
title: "How will you add a column to a pandas data frame?"
datePublished: Thu Mar 09 2023 09:51:57 GMT+0000 (Coordinated Universal Time)
cuid: clf0xjhcp00150ajy1q2e4w6z
slug: how-will-you-add-a-column-to-a-pandas-data-frame
tags: add-a-column-to-a-pandas-data-frame

---

To add a column to a Pandas DataFrame, you can use any of the following approaches:

1. Add a column with a scalar value:
    

You can add a new column with a scalar value by assigning the value to a new column label, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})

df['Gender'] = 'Male'
print(df)
```

Output:

```python
    Name  Age Gender
0   John   25   Male
1   Mike   32   Male
2  Sarah   28   Male
```

1. Add a column with a list or an array:
    

You can also add a new column with a list or an array of values by assigning the list to a new column label, like this:

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

1. Add a column with a function:
    

You can add a new column with a function that computes the values for each row by using the apply() method, like this:

```python
import pandas as pd

df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})

def get_gender(age):
    if age < 30:
        return 'Male'
    else:
        return 'Female'

df['Gender'] = df['Age'].apply(get_gender)
print(df)
```

Output:

```python
    Name  Age  Gender
0   John   25    Male
1   Mike   32  Female
2  Sarah   28    Male
```

In each of the above examples, we create a new column by assigning a new label to the DataFrame and providing the values for that column as a scalar, a list or an array, or a function that computes the values for each row.