---
title: "best ways to communicate with SQL server in dotnet wih code snippets"
datePublished: Sat Mar 04 2023 10:25:30 GMT+0000 (Coordinated Universal Time)
cuid: clettjd95000j08l0ao4f3a2z
slug: best-ways-to-communicate-with-sql-server-in-dotnet-wih-code-snippets
tags: best-ways-to-communicate-with-sql-server-in-dotnet-wih-code-snippets

---

here are some code snippets demonstrating best practices for communicating with SQL Server in .NET:

1. Establishing a connection to SQL Server using [ADO.NET](http://ADO.NET):
    

```csharp
using System.Data.SqlClient;

// Connection string for SQL Server
string connectionString = "Data Source=ServerName;Initial Catalog=DatabaseName;User ID=UserName;Password=Password";

// Create a SqlConnection object
using (SqlConnection connection = new SqlConnection(connectionString))
{
    // Open the connection
    connection.Open();

    // Use the connection to execute SQL commands
    // ...

    // Close the connection
    connection.Close();
}
```

1. Executing a stored procedure in SQL Server using [ADO.NET](http://ADO.NET):
    

```csharp
using System.Data;
using System.Data.SqlClient;

// Create a SqlConnection object
using (SqlConnection connection = new SqlConnection(connectionString))
{
    // Create a SqlCommand object for the stored procedure
    SqlCommand command = new SqlCommand("spName", connection);
    command.CommandType = CommandType.StoredProcedure;

    // Add input parameters to the stored procedure
    command.Parameters.AddWithValue("@param1", value1);
    command.Parameters.AddWithValue("@param2", value2);

    // Open the connection
    connection.Open();

    // Execute the stored procedure
    SqlDataReader reader = command.ExecuteReader();

    // Process the results
    while (reader.Read())
    {
        // ...
    }

    // Close the reader and connection
    reader.Close();
    connection.Close();
}
```

1. Executing a parameterized query in SQL Server using [ADO.NET](http://ADO.NET):
    

```csharp
using System.Data.SqlClient;

// Create a SqlConnection object
using (SqlConnection connection = new SqlConnection(connectionString))
{
    // Create a SqlCommand object for the query
    SqlCommand command = new SqlCommand("SELECT * FROM TableName WHERE ColumnName = @value", connection);

    // Add a parameter to the query
    command.Parameters.AddWithValue("@value", value);

    // Open the connection
    connection.Open();

    // Execute the query and process the results
    SqlDataReader reader = command.ExecuteReader();
    while (reader.Read())
    {
        // ...
    }

    // Close the reader and connection
    reader.Close();
    connection.Close();
}
```

1. Using transactions in SQL Server with [ADO.NET](http://ADO.NET):
    

```csharp
using System.Data.SqlClient;

// Create a SqlConnection object
using (SqlConnection connection = new SqlConnection(connectionString))
{
    // Open the connection
    connection.Open();

    // Begin a transaction
    SqlTransaction transaction = connection.BeginTransaction();

    try
    {
        // Create a SqlCommand object within the transaction
        SqlCommand command = connection.CreateCommand();
        command.Transaction = transaction;
        command.CommandText = "INSERT INTO TableName (ColumnName) VALUES (@value)";
        command.Parameters.AddWithValue("@value", value);

        // Execute the command
        command.ExecuteNonQuery();

        // Commit the transaction
        transaction.Commit();
    }
    catch (Exception ex)
    {
        // Roll back the transaction if an exception occurs
        transaction.Rollback();

        // Handle the exception
        // ...
    }

    // Close the connection
    connection.Close();
}
```

1. Using Dapper to execute a parameterized query:
    

```csharp
using Dapper;
using System.Collections.Generic;
using System.Data.SqlClient;

// Create a SqlConnection object
using (SqlConnection connection = new SqlConnection(connectionString))
{
    // Open the connection
    connection.Open();

    // Define the query and parameters using anonymous types
    string query = "SELECT * FROM TableName WHERE ColumnName = @value";
    var parameters = new { value = value };

    // Execute the query and return a list of results
    List<TableName> results = connection.Query<TableName>(query, parameters).ToList();

    // Close the connection
    connection.Close();
}
```

These are just some examples of