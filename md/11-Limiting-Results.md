### Lesson 11: Limiting Results

#### Using LIMIT
The `LIMIT` clause in SQL is used to specify the maximum number of records to return in a query result. This is particularly useful when you want to retrieve only a subset of data, such as when displaying results on a web page or when working with large datasets. The basic syntax for using `LIMIT` is:

```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number;
```

- **number**: The maximum number of records you want to retrieve.

**Example**: To select the first 5 customers from the `customers` table:

```sql
SELECT * FROM customers
LIMIT 5;
```

This query will return the first 5 rows from the `customers` table.

#### Using OFFSET
The `OFFSET` clause is often used in conjunction with `LIMIT` to skip a specified number of records before starting to return rows. This is useful for pagination, where you want to display results in chunks. The basic syntax for using `LIMIT` with `OFFSET` is:

```sql
SELECT column1, column2, ...
FROM table_name
LIMIT number OFFSET offset_value;
```

- **number**: The maximum number of records to return.
- **offset_value**: The number of records to skip before starting to return rows.

**Example**: To select 5 customers starting from the 6th record (skipping the first 5):

```sql
SELECT * FROM customers
LIMIT 5 OFFSET 5;
```

Alternatively, you can also use the `LIMIT` clause with two arguments, where the first argument is the offset and the second argument is the limit:

```sql
SELECT * FROM customers
LIMIT 5, 5;
```

In this case, the query will skip the first 5 records and return the next 5 records.

### Summary
Using the `LIMIT` and `OFFSET` clauses allows you to control the number of records returned by your queries, making it easier to manage large datasets and implement pagination in your applications. By mastering these clauses, you can enhance the efficiency and usability of your SQL queries, retrieving only the data you need when you need it.