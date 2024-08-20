### Lesson 8: SELECT Statement

#### Basic SELECT Syntax
The `SELECT` statement is used to query data from a database. It allows you to retrieve specific information from one or more tables. The basic syntax for the `SELECT` statement is as follows:

```sql
SELECT column1, column2, ...
FROM table_name;
```

- **column1, column2, ...**: The names of the columns you want to retrieve. You can specify multiple columns separated by commas.
- **table_name**: The name of the table from which you want to retrieve data.

**Example**: To select all columns from the `customers` table:

```sql
SELECT * FROM customers;
```

The asterisk (`*`) is a wildcard that represents all columns in the table.

#### Selecting Specific Columns
When you only want to retrieve specific columns from a table, you can list the column names in the `SELECT` statement. This helps to reduce the amount of data returned and makes it easier to work with.

**Example**: To select only the `name` and `email` columns from the `customers` table:

```sql
SELECT name, email FROM customers;
```

This query will return a result set containing only the `name` and `email` columns for all customers in the table.

#### Using Aliases for Columns
Aliases are temporary names that you can assign to columns or tables in your query. They can make your output more readable or help clarify the purpose of a column. You create an alias using the `AS` keyword (though `AS` is optional).

The syntax for using an alias is:

```sql
SELECT column_name AS alias_name
FROM table_name;
```

**Example**: To rename the `name` column to `Customer Name` in the output:

```sql
SELECT name AS `Customer Name`, email FROM customers;
```

You can also use aliases for calculations or functions. For example, if you want to calculate the total price of an order and give it an alias:

```sql
SELECT product_name, price, quantity, (price * quantity) AS total_price
FROM orders;
```

### Summary
The `SELECT` statement is a fundamental part of SQL that allows you to retrieve data from your database. By mastering the basic syntax, selecting specific columns, and using aliases, you can create clear and efficient queries to extract the information you need. This is essential for analyzing and manipulating data in your applications.