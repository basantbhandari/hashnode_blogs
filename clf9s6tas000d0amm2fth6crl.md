---
title: "combine dataframes in pandas?"
datePublished: Wed Mar 15 2023 14:32:03 GMT+0000 (Coordinated Universal Time)
cuid: clf9s6tas000d0amm2fth6crl
slug: combine-dataframes-in-pandas
tags: combine-dataframes-in-pandas

---

you can combine dataframes in Pandas using various methods. Here are some common ways to combine dataframes:

1. Concatenation: You can concatenate two or more dataframes along a specified axis (either rows or columns) using the `concat()` function. For example, to concatenate two dataframes `df1` and `df2` along the rows, you can use:
    

```sql
result = pd.concat([df1, df2], axis=0)
```

Here, `axis=0` means concatenating the dataframes along the rows. Similarly, `axis=1` means concatenating along the columns.

1. Joining: You can join two dataframes based on a common column using the `merge()` function. For example, to join two dataframes `df1` and `df2` on a column named `key`, you can use:
    

```sql
result = pd.merge(df1, df2, on='key')
```

Here, `on='key'` specifies the column to join on.

1. Appending: You can append rows of one dataframe to another dataframe using the `append()` function. For example, to append rows of `df2` to `df1`, you can use:
    

```sql
result = df1.append(df2)
```

Here, `df2` is appended to `df1` along the rows.

1. Merging: You can merge two dataframes with different column names using the `merge()` function and specifying the column names to join on using the `left_on` and `right_on` parameters. For example, to merge two dataframes `df1` and `df2` with columns named `key1` and `key2`, you can use:
    

```sql
result = pd.merge(df1, df2, left_on='key1', right_on='key2')
```

Here, `left_on='key1'` specifies the column in `df1` to join on and `right_on='key2'` specifies the column in `df2` to join on.

These are some common ways to combine data frames in Pandas.