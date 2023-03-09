---
title: "Adding Rows to a DataFrame"
datePublished: Thu Mar 09 2023 10:17:39 GMT+0000 (Coordinated Universal Time)
cuid: clf0ygj4d00050ajv21jp4yov
slug: adding-rows-to-a-dataframe
tags: adding-rows-to-a-dataframe

---

To add rows to a Pandas data frame, we can use the `.loc`, `.iloc`, and `.ix` indexing operators.

* `.loc` works based on the labels of the index. For example, `df.loc[4]` would insert a row with an index label of 4.
    
* `.iloc` works based on the position of the index. For example, `df.iloc[4]` would insert a row at the 4th position of the index.
    
* `.ix` is a more complex case. If the index is integer-based, we can use it to reference the label, as with `.loc`. Otherwise, it works based on position, like `.iloc`.
    

In all cases, the row to be inserted is specified as a new Pandas Series or dictionary object containing the values for each column in the DataFrame.

Sure, here are some examples of how to add rows to a Pandas data frame using `.loc`, `.iloc`, and `.ix`:

```python
import pandas as pd

# Create a DataFrame with two columns
df = pd.DataFrame({'Name': ['John', 'Mike', 'Sarah'], 'Age': [25, 32, 28]})

# Use .loc to insert a new row with label 3
df.loc[3] = ['Tom', 30]

# Use .iloc to insert a new row at position 0
df.iloc[0] = ['Peter', 35]

# Use .ix to insert a new row with label 4 or position 4, depending on the index type
df.ix[4] = ['Mary', 26]

# Print the DataFrame to see the new rows
print(df)
```

Output:

```python
    Name  Age
0  Peter   35
1   Mike   32
2  Sarah   28
3    Tom   30
4   Mary   26
```

In each case, we create a new row as a list of values for the columns in the DataFrame and use the appropriate indexing operator to insert it into the DataFrame. Note that using `.loc` and `.ix` to insert rows that don't exist in the DataFrame will create a new row with that label while using `.iloc` to insert a row at a position greater than the current length of the data frame will cause an error.