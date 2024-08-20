### Lesson 15: Inserting Data

#### INSERT INTO Syntax
The `INSERT INTO` statement is used to add new records (rows) to a table in a database. The basic syntax for inserting data into a table is as follows:

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

- **table_name**: The name of the table where you want to insert data.
- **column1, column2, ...**: The names of the columns that you want to populate.
- **value1, value2, ...**: The corresponding values for each column.

**Example**: To insert a new customer into the `customers` table:

```sql
INSERT INTO customers (name, email, phone)
VALUES ('Alice Smith', 'alice@example.com', '123-456-7890');
```

#### Inserting Multiple Rows
You can insert multiple rows in a single `INSERT INTO` statement by separating each set of values with commas. This approach can improve performance by reducing the number of individual insert operations.

**Example**: To insert multiple customers at once:

```sql
INSERT INTO customers (name, email, phone)
VALUES 
    ('Bob Johnson', 'bob@example.com', '234-567-8901'),
    ('Carol White', 'carol@example.com', '345-678-9012'),
    ('David Brown', 'david@example.com', '456-789-0123');
```

This query will add three new customers to the `customers` table in one operation.

#### Using INSERT ... SELECT
The `INSERT ... SELECT` statement allows you to insert data into a table based on the results of a `SELECT` query. This is useful for copying data from one table to another or inserting data that meets specific criteria.

**Example**: To insert all customers from the `old_customers` table into the `customers` table:

```sql
INSERT INTO customers (name, email, phone)
SELECT name, email, phone
FROM old_customers;
```

In this example, the `SELECT` statement retrieves the names, emails, and phone numbers from the `old_customers` table, and the `INSERT INTO` statement adds those records to the `customers` table.

### Summary
Inserting data into a table is a fundamental operation in SQL, and understanding the `INSERT INTO` syntax is essential for managing your database. By mastering how to insert single and multiple rows, as well as using the `INSERT ... SELECT` statement, you can efficiently populate your tables with the data you need. This skill is crucial for maintaining and updating your database effectively.