# different execute method of ADO.NET

[ADO.NET](http://ADO.NET) provides several different methods for executing queries and commands against a data source, including:

1. ExecuteNonQuery: This method is used to execute SQL commands that do not return any data, such as INSERT, UPDATE, DELETE, and CREATE statements. The ExecuteNonQuery method returns the number of rows affected by the command.
    
2. ExecuteScalar: This method is used to execute SQL commands that return a single value, such as SELECT COUNT(\*) statements. The ExecuteScalar method returns the first column of the first row in the result set.
    
3. ExecuteReader: This method is used to execute SQL commands that return one or more rows of data, such as SELECT statements. The ExecuteReader method returns a DataReader object that provides a forward-only, read-only stream of data from the result set.
    
4. ExecuteXmlReader: This method is used to execute SQL commands that return XML data. The ExecuteXmlReader method returns an XmlReader object that provides a forward-only, read-only stream of XML data from the result set.
    

These methods provide a flexible and efficient way to execute SQL commands against a data source and retrieve the results. The choice of method depends on the type of command being executed and the type of data being returned. By using the appropriate method, developers can create efficient and scalable data access solutions that meet the needs of their applications.