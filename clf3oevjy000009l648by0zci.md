---
title: "GroupBy in Pandas?"
datePublished: Sat Mar 11 2023 07:59:44 GMT+0000 (Coordinated Universal Time)
cuid: clf3oevjy000009l648by0zci
slug: groupby-in-pandas
tags: groupby-in-pandas

---

GroupBy is a common operation in Pandas that allows you to group a DataFrame by one or more columns and apply a function to each group. This can be useful for tasks such as data aggregation, summary statistics, and data analysis.

To use GroupBy in Pandas, you can start by creating a DataFrame and specifying the column(s) you want to group by. For example, let's say you have a data frame with sales data for different products and regions:

```python
import pandas as pd

data = {
    'Product': ['A', 'A', 'B', 'B', 'B', 'C', 'C', 'C'],
    'Region': ['North', 'South', 'North', 'South', 'West', 'North', 'South', 'West'],
    'Sales': [100, 200, 150, 250, 300, 175, 225, 250]
}

df = pd.DataFrame(data)
```

You can group this DataFrame by the 'Product' column and calculate the mean sales for each product using the `groupby()` method:

```python
grouped = df.groupby('Product')
mean_sales = grouped['Sales'].mean()
```

This will give you a new Series with the mean sales for each product:

```python
Product
A    150.0
B    233.333333
C    216.666667
Name: Sales, dtype: float64
```

You can also group by multiple columns by passing a list of column names to `groupby()`. For example, to group by both 'Product' and 'Region':

```python
grouped = df.groupby(['Product', 'Region'])
```

Once you have grouped the DataFrame, you can apply various functions to each group using the `agg()` method. For example, to calculate the sum and count of sales for each product:

```python
sales_summary = grouped['Sales'].agg(['sum', 'count'])
```

This will give you a new DataFrame with the sum and count of sales for each combination of product and region:

```python
                sum  count
Product Region            
A       North   100      1
        South   200      1
B       North   150      1
        South   250      1
        West    300      1
C       North   175      1
        South   225      1
        West    250      1
```