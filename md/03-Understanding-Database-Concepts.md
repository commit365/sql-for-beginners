### Lesson 3: Understanding Database Concepts

#### Tables, Rows, and Columns
In a relational database, data is organized into tables, which are the fundamental structures for storing information. Each table consists of:

- **Tables**: A table is a collection of related data entries and consists of rows and columns. Each table represents a specific entity, such as customers, products, or orders.

- **Rows**: Each row (or record) in a table represents a single instance of the entity. For example, in a "Customers" table, each row would contain information about one customer.

- **Columns**: Each column represents a specific attribute of the entity. For example, in a "Customers" table, columns might include "CustomerID," "Name," "Email," and "Phone Number." Each column has a defined data type that determines what kind of data it can hold.

#### Primary Keys and Foreign Keys
Keys are essential for maintaining the integrity and relationships of data within a database.

- **Primary Key**: A primary key is a unique identifier for each record in a table. It ensures that no two rows have the same value for this column. For example, the "CustomerID" column in a "Customers" table could serve as the primary key, uniquely identifying each customer.

- **Foreign Key**: A foreign key is a field in one table that links to the primary key of another table. This establishes a relationship between the two tables. For example, in an "Orders" table, the "CustomerID" column could be a foreign key that references the "CustomerID" in the "Customers" table, indicating which customer placed each order.

#### Data Types in MySQL
Data types define the kind of data that can be stored in a column. MySQL supports various data types, which can be categorized as follows:

- **Numeric Types**: Used for storing numbers. Examples include:
  - `INT`: Integer values
  - `FLOAT`: Floating-point numbers
  - `DECIMAL`: Fixed-point numbers

- **String Types**: Used for storing text. Examples include:
  - `VARCHAR`: Variable-length strings
  - `CHAR`: Fixed-length strings
  - `TEXT`: Long text strings

- **Date and Time Types**: Used for storing date and time values. Examples include:
  - `DATE`: Date values (YYYY-MM-DD)
  - `TIME`: Time values (HH:MM:SS)
  - `DATETIME`: Date and time values

Choosing the appropriate data type is crucial for optimizing performance and ensuring data integrity.

#### Understanding Schemas and Databases
A schema is a logical structure that defines how data is organized in a database. It provides a blueprint for how tables and relationships are structured. Key concepts include:

- **Database**: A database is a collection of related tables and schemas. It serves as a container for storing data and managing its organization.

- **Schema**: A schema defines the tables, fields, data types, and relationships within a database. It helps to organize and categorize data logically. For example, a database for an e-commerce application might have schemas for "Customers," "Orders," "Products," and "Payments."

In MySQL, you can create multiple databases, each with its own schema, allowing for better organization and separation of data. Understanding schemas and databases is essential for designing efficient and scalable database systems.