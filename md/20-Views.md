### Lesson 20: Views

#### What are Views?
A view in SQL is a virtual table that is based on the result of a SELECT query. It does not store the data itself but provides a way to present data from one or more tables in a specific format. Views can simplify complex queries, enhance security by restricting access to specific columns or rows, and provide a consistent interface for users.

**Key Characteristics of Views**:
- **Virtual Table**: Views do not store data; they display data stored in tables.
- **Simplification**: They can encapsulate complex queries, making it easier for users to retrieve data without needing to understand the underlying table structure.
- **Security**: Views can limit user access to specific data, allowing for more controlled data exposure.

#### Creating and Using Views
To create a view, you use the `CREATE VIEW` statement, followed by the view name and the SELECT query that defines the view. The basic syntax is:

```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

**Example**: To create a view that shows customer names and their total order amounts:

```sql
CREATE VIEW customer_orders AS
SELECT c.name, SUM(o.total_amount) AS total_spent
FROM customers c
JOIN orders o ON c.customer_id = o.customer_id
GROUP BY c.name;
```

Once the view is created, you can query it just like a regular table:

```sql
SELECT * FROM customer_orders;
```

This query will return the names of customers along with their total spending.

#### Updatable vs. Non-Updatable Views
Views can be categorized as updatable or non-updatable based on whether you can modify the data through the view.

- **Updatable Views**: These views allow you to perform `INSERT`, `UPDATE`, or `DELETE` operations on the underlying tables through the view. For a view to be updatable, it must meet certain criteria:
  - It must select from a single table.
  - It cannot contain aggregate functions, GROUP BY, or DISTINCT clauses.

  **Example**: If you have a simple view that selects from a single table:
  ```sql
  CREATE VIEW active_customers AS
  SELECT * FROM customers WHERE status = 'active';
  ```

  You can update the underlying `customers` table through this view:
  ```sql
  UPDATE active_customers
  SET email = 'new_email@example.com'
  WHERE customer_id = 1;
  ```

- **Non-Updatable Views**: These views do not allow modifications to the underlying data. They typically involve multiple tables, aggregate functions, or complex queries.

  **Example**: A view that calculates totals:
  ```sql
  CREATE VIEW order_summary AS
  SELECT customer_id, COUNT(*) AS order_count, SUM(total_amount) AS total_spent
  FROM orders
  GROUP BY customer_id;
  ```

  Attempting to update this view will result in an error, as it is not possible to determine how to apply the changes to the underlying `orders` table.

### Summary
Views are a powerful feature in SQL that provide a way to simplify data access and enhance security. By understanding how to create and use views, as well as the differences between updatable and non-updatable views, you can effectively manage how data is presented and interacted with in your database. This knowledge is essential for developing user-friendly and secure database applications.