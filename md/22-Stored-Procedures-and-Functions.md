### Lesson 22: Stored Procedures and Functions

#### What are Stored Procedures?
Stored procedures are precompiled collections of SQL statements and optional control-flow statements that are stored in the database. They can be executed as a single unit, allowing for efficient execution of complex operations. Stored procedures help encapsulate business logic, reduce code duplication, and improve performance by minimizing the amount of SQL code sent to the database.

**Key Benefits of Stored Procedures**:
- **Modularity**: Stored procedures allow you to break down complex operations into manageable pieces.
- **Reusability**: Once created, stored procedures can be reused in multiple applications or queries.
- **Performance**: Stored procedures are compiled and optimized by the database engine, leading to faster execution.
- **Security**: They can help control access to data by limiting direct access to tables and allowing users to execute procedures instead.

#### Creating and Executing Stored Procedures
To create a stored procedure, you use the `CREATE PROCEDURE` statement. The basic syntax is as follows:

```sql
CREATE PROCEDURE procedure_name (parameters)
BEGIN
    -- SQL statements
END;
```

- **procedure_name**: The name of the stored procedure.
- **parameters**: Optional input and output parameters.
- **SQL statements**: The SQL code that the stored procedure will execute.

**Example**: Creating a stored procedure to retrieve customer details by `customer_id`:

```sql
CREATE PROCEDURE GetCustomerDetails(IN cust_id INT)
BEGIN
    SELECT * FROM customers WHERE customer_id = cust_id;
END;
```

To execute the stored procedure, you use the `CALL` statement:

```sql
CALL GetCustomerDetails(1);
```

This command will execute the stored procedure and return the details of the customer with `customer_id` 1.

#### Understanding User-Defined Functions (UDFs)
User-defined functions (UDFs) are similar to stored procedures but are designed to return a single value or a table and can be used in SQL expressions. UDFs can be used in SELECT statements, WHERE clauses, and anywhere an expression is valid.

**Key Characteristics of UDFs**:
- **Return Value**: UDFs must return a value, which can be a scalar value (like INT, VARCHAR) or a table.
- **Deterministic vs. Non-Deterministic**: UDFs can be deterministic (always return the same result for the same input) or non-deterministic (may return different results).

**Creating a UDF**: The basic syntax for creating a UDF is as follows:

```sql
CREATE FUNCTION function_name (parameters)
RETURNS return_data_type
BEGIN
    -- SQL statements
    RETURN value;
END;
```

**Example**: Creating a UDF to calculate the total order amount for a specific customer:

```sql
CREATE FUNCTION GetTotalOrderAmount(cust_id INT)
RETURNS DECIMAL(10, 2)
BEGIN
    DECLARE total DECIMAL(10, 2);
    SELECT SUM(total_amount) INTO total FROM orders WHERE customer_id = cust_id;
    RETURN total;
END;
```

To use the UDF in a query:

```sql
SELECT name, GetTotalOrderAmount(customer_id) AS total_spent
FROM customers;
```

### Summary
Stored procedures and user-defined functions (UDFs) are powerful tools in SQL that allow you to encapsulate business logic and perform complex operations efficiently. By understanding how to create and execute stored procedures, as well as how to define and use UDFs, you can enhance the functionality of your database applications. These features promote code reuse, improve performance, and provide a structured way to manage database operations.