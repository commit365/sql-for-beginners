### Lesson 10: Sorting Results

#### ORDER BY Clause
The `ORDER BY` clause in SQL is used to sort the result set of a query based on one or more columns. By default, the sorting is done in ascending order, but you can also specify descending order. The basic syntax for the `ORDER BY` clause is:

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column_name [ASC|DESC];
```

- **column_name**: The name of the column by which you want to sort the results.
- **ASC**: Sorts the results in ascending order (default).
- **DESC**: Sorts the results in descending order.

**Example**: To select all customers from the `customers` table and sort them by their last names in ascending order:

```sql
SELECT * FROM customers
ORDER BY last_name ASC;
```

If you want to sort in descending order, you can use:

```sql
SELECT * FROM customers
ORDER BY last_name DESC;
```

#### Sorting by Multiple Columns
You can sort the results by multiple columns by listing the column names in the `ORDER BY` clause, separated by commas. The sorting will be applied in the order you specify.

**Example**: To sort customers first by `city` in ascending order and then by `last_name` in descending order:

```sql
SELECT * FROM customers
ORDER BY city ASC, last_name DESC;
```

In this example, the result set will be sorted by `city` first. If multiple customers are in the same city, they will then be sorted by `last_name` within that city.

### Summary
The `ORDER BY` clause is a powerful tool for organizing your query results in a meaningful way. By sorting data based on one or more columns, you can enhance the readability of your results and make it easier to analyze information. Understanding how to use sorting effectively is an essential skill in SQL that helps you present data in a structured format.