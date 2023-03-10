---
title: "difference between COALESCE, ISNULL and NULLIF"
datePublished: Fri Mar 10 2023 14:14:05 GMT+0000 (Coordinated Universal Time)
cuid: clf2mcgbt00020alc64fz4iwc
slug: difference-between-coalesce-isnull-and-nullif
tags: difference-between-coalesce-isnull-and-nullif

---

`COALESCE`, `ISNULL`, and `NULLIF` are all functions used to handle null values in SQL, but they have some differences:

1. `COALESCE` is a standard SQL function, while `ISNULL` and `NULLIF` are specific to T-SQL.
    
2. `COALESCE` and `ISNULL` return the first non-null value from a list of expressions, but `ISNULL` replaces null values with a specified value, while `COALESCE` does not.
    
3. `NULLIF` returns null if two expressions are equal, otherwise it returns the first expression.
    
4. `COALESCE` and `ISNULL` can take any number of parameters, while `NULLIF` takes exactly two parameters.
    
5. `COALESCE` evaluates each expression in order until it finds a non-null value, while `ISNULL` always returns the second parameter if the first parameter is null.
    
6. `NULLIF` compares two expressions and returns null if they are equal, while `COALESCE` and `ISNULL` do not compare expressions.
    
7. `COALESCE` can be nested to handle more complex expressions and conditions, while `ISNULL` and `NULLIF` cannot.
    
8. `COALESCE` returns the data type of the first non-null expression in the list, while `ISNULL` returns the data type of the second parameter.
    
9. `NULLIF` returns the data type of the first parameter.
    
10. `COALESCE` is more versatile than `ISNULL` and `NULLIF`, as it can handle multiple expressions and different data types.
    
11. `ISNULL` is more efficient than `COALESCE`, as it only evaluates two expressions, whereas `COALESCE` evaluates all expressions in the list.
    
12. `NULLIF` is typically used in comparisons or calculations where null values could cause errors or incorrect results.
    
13. `COALESCE` is often used to provide default values for nulls in queries or to handle null values in computed columns.
    
14. `ISNULL` is commonly used to replace null values with a specific value for display or reporting purposes.