### Lesson 7: Modifying Tables

#### ALTER TABLE Syntax
The `ALTER TABLE` statement in MySQL is used to modify an existing table's structure. You can use this command to add, modify, or drop columns, as well as to change other properties of the table. The basic syntax for the `ALTER TABLE` command is:

```sql
ALTER TABLE table_name action;
```

- **table_name**: The name of the table you want to modify.
- **action**: The specific modification you want to perform (e.g., ADD, MODIFY, DROP).

#### Adding Columns
To add a new column to an existing table, use the `ADD` keyword followed by the column definition. Here’s the syntax:

```sql
ALTER TABLE table_name ADD column_name data_type [constraints];
```

**Example**: Adding a new column called `address` to the `customers` table:

```sql
ALTER TABLE customers ADD address VARCHAR(255);
```

You can also add multiple columns in a single command:

```sql
ALTER TABLE customers 
ADD date_of_birth DATE,
ADD membership_status VARCHAR(20);
```

#### Modifying Columns
To change the definition of an existing column, use the `MODIFY` keyword. This allows you to change the data type, constraints, or other attributes of the column. The syntax is as follows:

```sql
ALTER TABLE table_name MODIFY column_name new_data_type [new_constraints];
```

**Example**: Modifying the `phone` column in the `customers` table to increase its length:

```sql
ALTER TABLE customers MODIFY phone VARCHAR(20);
```

You can also change a column's constraints. For example, to make the `email` column nullable:

```sql
ALTER TABLE customers MODIFY email VARCHAR(100) NULL;
```

#### Dropping Columns
To remove a column from an existing table, use the `DROP` keyword. The syntax is:

```sql
ALTER TABLE table_name DROP COLUMN column_name;
```

**Example**: Dropping the `address` column from the `customers` table:

```sql
ALTER TABLE customers DROP COLUMN address;
```

**Important Note**: Dropping a column will permanently remove all data stored in that column, so use this command with caution.

### Summary
By using the `ALTER TABLE` statement, you can effectively modify the structure of your tables in MySQL. Whether you need to add new columns, change existing ones, or remove unnecessary columns, understanding how to use `ALTER TABLE` is essential for maintaining and evolving your database schema as your application requirements change.