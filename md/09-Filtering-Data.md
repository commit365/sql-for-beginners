### Lesson 9: Filtering Data

#### Using the WHERE Clause
The `WHERE` clause is used in SQL to filter records based on specific conditions. It allows you to retrieve only the rows that meet certain criteria, making your queries more precise and relevant. The basic syntax for using the `WHERE` clause is:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

- **condition**: This specifies the criteria that must be met for a row to be included in the result set.

**Example**: To select customers from the `customers` table who live in "New York":

```sql
SELECT * FROM customers
WHERE city = 'New York';
```

This query will return all columns for customers whose city is "New York".

#### Comparison Operators and Logical Operators
When filtering data, you can use various comparison operators to define your conditions. Common comparison operators include:

- **=`**: Equal to
- **!=** or **<>**: Not equal to
- **>**: Greater than
- **<**: Less than
- **>=**: Greater than or equal to
- **<=**: Less than or equal to

You can also combine multiple conditions using logical operators:

- **AND**: Both conditions must be true.
- **OR**: At least one of the conditions must be true.
- **NOT**: Negates a condition.

**Example**: To select customers who are older than 30 and live in "Los Angeles":

```sql
SELECT * FROM customers
WHERE age > 30 AND city = 'Los Angeles';
```

**Example**: To select customers who are either from "Chicago" or "Houston":

```sql
SELECT * FROM customers
WHERE city = 'Chicago' OR city = 'Houston';
```

#### Using LIKE for Pattern Matching
The `LIKE` operator is used to search for a specified pattern in a column. It is particularly useful for filtering string data. The basic syntax is:

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE pattern;
```

- **pattern**: The pattern can include wildcard characters:
  - **`%`**: Represents zero or more characters.
  - **`_`**: Represents a single character.

**Example**: To find customers whose names start with "J":

```sql
SELECT * FROM customers
WHERE name LIKE 'J%';
```

This query will return all customers whose names begin with the letter "J".

**Example**: To find customers whose email addresses contain "gmail":

```sql
SELECT * FROM customers
WHERE email LIKE '%gmail%';
```

This query will return all customers with email addresses that include "gmail" anywhere in the address.

### Summary
Filtering data using the `WHERE` clause is essential for retrieving specific records from your database. By employing comparison operators, logical operators, and the `LIKE` operator for pattern matching, you can create powerful queries that provide meaningful insights from your data. Understanding how to effectively filter data is a crucial skill in SQL that enhances your ability to analyze and manipulate information.