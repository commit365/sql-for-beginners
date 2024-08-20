### Lesson 6: Creating Tables

#### Table Creation Syntax
Creating a table in MySQL involves using the `CREATE TABLE` statement, which defines the structure of the table, including its name and the columns it contains. The basic syntax for creating a table is as follows:

```sql
CREATE TABLE table_name (
    column_name1 data_type constraints,
    column_name2 data_type constraints,
    ...
);
```

- **table_name**: The name you want to give to your new table.
- **column_name**: The name of each column in the table.
- **data_type**: The type of data that can be stored in the column (e.g., INT, VARCHAR).
- **constraints**: Optional rules that apply to the column (e.g., NOT NULL, UNIQUE).

#### Defining Columns and Data Types
When creating a table, you need to specify the columns and their corresponding data types. Here are some commonly used data types in MySQL:

- **Numeric Types**:
  - `INT`: Integer values (e.g., 1, 100, -50)
  - `FLOAT`: Floating-point numbers (e.g., 3.14, -0.001)
  - `DECIMAL(p, s)`: Fixed-point numbers, where `p` is the total number of digits and `s` is the number of digits after the decimal point.

- **String Types**:
  - `VARCHAR(n)`: Variable-length strings with a maximum length of `n` characters (e.g., `VARCHAR(50)`).
  - `CHAR(n)`: Fixed-length strings (e.g., `CHAR(10)`).
  - `TEXT`: Long text strings for larger amounts of text.

- **Date and Time Types**:
  - `DATE`: Date values in the format YYYY-MM-DD.
  - `TIME`: Time values in the format HH:MM:SS.
  - `DATETIME`: Date and time values.

**Example**: Creating a table called `customers` with various columns:
```sql
CREATE TABLE customers (
    customer_id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    email VARCHAR(100) UNIQUE,
    phone VARCHAR(15),
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

#### Constraints
Constraints are rules applied to columns to enforce data integrity. Here are some common constraints you can use when creating tables:

- **NOT NULL**: Ensures that a column cannot have a NULL value. This is useful for mandatory fields.
  ```sql
  name VARCHAR(50) NOT NULL
  ```

- **UNIQUE**: Ensures that all values in a column are distinct, preventing duplicate entries.
  ```sql
  email VARCHAR(100) UNIQUE
  ```

- **DEFAULT**: Sets a default value for a column if no value is provided during the insertion of a new record.
  ```sql
  created_at DATETIME DEFAULT CURRENT_TIMESTAMP
  ```

- **CHECK**: Ensures that all values in a column satisfy a specific condition. Note that support for CHECK constraints may vary by MySQL version.
  ```sql
  age INT CHECK (age >= 0)
  ```

**Example**: Here’s how you might use constraints when creating a table:
```sql
CREATE TABLE products (
    product_id INT AUTO_INCREMENT PRIMARY KEY,
    product_name VARCHAR(100) NOT NULL,
    price DECIMAL(10, 2) NOT NULL CHECK (price >= 0),
    stock INT DEFAULT 0,
    created_at DATETIME DEFAULT CURRENT_TIMESTAMP
);
```

By understanding the table creation syntax, how to define columns and data types, and how to apply constraints, you can effectively design and implement tables in your MySQL database. This is a crucial step in organizing your data for efficient storage and retrieval.