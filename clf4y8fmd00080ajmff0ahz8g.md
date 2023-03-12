---
title: "SQL Function and Stored Procedure?"
datePublished: Sun Mar 12 2023 05:22:26 GMT+0000 (Coordinated Universal Time)
cuid: clf4y8fmd00080ajmff0ahz8g
slug: sql-function-and-stored-procedure
tags: sql-function-and-stored-procedure

---

SQL functions and stored procedures are both database objects that can be created and used within an SQL database.

A SQL function is a named routine that returns a value. It is similar to a mathematical function in that it takes one or more input parameters, performs a calculation, and returns a single value. Functions are typically used to perform calculations or data manipulations that return a single value, such as calculating the average of a set of values or formatting a date.

A SQL stored procedure is a named routine that can perform one or more operations on a database. Unlike a function, a stored procedure does not return a value; instead, it can perform various data manipulation tasks such as inserting, updating, deleting, and selecting data from one or more tables. Stored procedures can also accept input parameters and return output parameters, making them flexible and versatile.

One key difference between functions and stored procedures is that functions are typically used as part of an SQL query, whereas stored procedures are typically called from an application or other programming language. Functions are also deterministic, meaning they always return the same result for the same input parameters, whereas stored procedures can have side effects and may not always return the same result for the same input.

In summary, SQL functions and stored procedures are both database objects that can perform various data manipulation tasks. Functions are used to perform calculations and return a single value, while stored procedures can perform multiple data manipulation tasks and accept input parameters and return output parameters.

here are examples of a SQL function and a stored procedure:

SQL Function Example: Let's create a simple SQL function named "GetAverageScore" that takes two parameters (score1 and score2) and returns their average:

```sql
CREATE FUNCTION GetAverageScore (@score1 INT, @score2 INT)
RETURNS FLOAT
AS
BEGIN
    DECLARE @avg FLOAT
    SET @avg = (@score1 + @score2) / 2.0
    RETURN @avg
END
```

Now, we can call this function in an SQL query to get the average score for a set of records:

```sql
SELECT StudentName, GetAverageScore(MathScore, EnglishScore) as AvgScore
FROM Students
```

Stored Procedure Example: Let's create a stored procedure named "UpdateProductPrice" that takes two parameters (productId and newPrice) and updates the price of a product in the "Products" table:

```sql
CREATE PROCEDURE UpdateProductPrice (@productId INT, @newPrice DECIMAL(10,2))
AS
BEGIN
    UPDATE Products
    SET Price = @newPrice
    WHERE ProductId = @productId
END
```

Now, we can call this stored procedure from an application or programming language to update the price of a product:

```sql
EXEC UpdateProductPrice 123, 9.99
```

This will update the price of the product with the ProductId of 123 to 9.99 in the "Products" table.