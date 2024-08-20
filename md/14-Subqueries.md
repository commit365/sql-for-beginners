### Lesson 14: Subqueries

#### What are Subqueries?
A subquery, also known as a nested query or inner query, is a query that is embedded within another SQL query. Subqueries are used to perform operations that require multiple steps, allowing you to retrieve data based on the results of another query. They can return single values, multiple values, or a complete result set, and they are enclosed in parentheses.

**Example**: A simple subquery to find customers who have placed orders:
```sql
SELECT name
FROM customers
WHERE customer_id IN (SELECT customer_id FROM orders);
```
In this example, the inner query retrieves all `customer_id`s from the `orders` table, and the outer query selects the names of customers whose IDs match those returned by the inner query.

#### Using Subqueries in SELECT, INSERT, UPDATE, and DELETE
Subqueries can be used in various SQL statements, including `SELECT`, `INSERT`, `UPDATE`, and `DELETE`. Here are examples of each:

- **Subquery in SELECT**: Retrieve data based on the result of another query.
  
  **Example**: Find the names of customers who have the highest order total:
  ```sql
  SELECT name
  FROM customers
  WHERE customer_id = (SELECT customer_id FROM orders ORDER BY total_amount DESC LIMIT 1);
  ```

- **Subquery in INSERT**: Insert data into a table based on the result of another query.
  
  **Example**: Insert a new order for a customer using their ID:
  ```sql
  INSERT INTO orders (customer_id, total_amount)
  VALUES ((SELECT customer_id FROM customers WHERE name = 'John Doe'), 100.00);
  ```

- **Subquery in UPDATE**: Update records in a table based on the result of another query.
  
  **Example**: Update the total amount for a specific order:
  ```sql
  UPDATE orders
  SET total_amount = 200.00
  WHERE order_id = (SELECT order_id FROM orders WHERE customer_id = 1 LIMIT 1);
  ```

- **Subquery in DELETE**: Delete records from a table based on the result of another query.
  
  **Example**: Delete all orders placed by a specific customer:
  ```sql
  DELETE FROM orders
  WHERE customer_id = (SELECT customer_id FROM customers WHERE name = 'Jane Doe');
  ```

#### Correlated vs. Non-Correlated Subqueries
Subqueries can be classified into two types: correlated and non-correlated subqueries.

- **Non-Correlated Subquery**: This type of subquery can be executed independently of the outer query. It does not reference any columns from the outer query.

  **Example**: A non-correlated subquery to find the average order total:
  ```sql
  SELECT AVG(total_amount)
  FROM orders;
  ```

- **Correlated Subquery**: This type of subquery depends on the outer query for its values. It references columns from the outer query and is executed once for each row processed by the outer query.

  **Example**: A correlated subquery to find customers who have placed orders above the average order total:
  ```sql
  SELECT name
  FROM customers c
  WHERE EXISTS (SELECT 1 FROM orders o WHERE o.customer_id = c.customer_id AND o.total_amount > (SELECT AVG(total_amount) FROM orders));
  ```

### Summary
Subqueries are a powerful feature in SQL that allow you to perform complex queries and operations by nesting one query inside another. By understanding how to use subqueries in `SELECT`, `INSERT`, `UPDATE`, and `DELETE` statements, as well as distinguishing between correlated and non-correlated subqueries, you can enhance your ability to manipulate and analyze data effectively. This skill is essential for writing efficient and sophisticated SQL queries in any relational database.