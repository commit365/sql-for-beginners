### Lesson 12: Using Aggregate Functions

#### COUNT, SUM, AVG, MIN, MAX
Aggregate functions in SQL are used to perform calculations on a set of values and return a single value. They are commonly used in conjunction with the `SELECT` statement to summarize data. Here are some of the most commonly used aggregate functions:

- **COUNT()**: Returns the number of rows that match a specified condition. It can count all rows or only non-NULL values in a column.
  
  **Example**: To count the total number of customers in the `customers` table:
  ```sql
  SELECT COUNT(*) FROM customers;
  ```

- **SUM()**: Returns the total sum of a numeric column.

  **Example**: To calculate the total sales from the `orders` table:
  ```sql
  SELECT SUM(total_amount) FROM orders;
  ```

- **AVG()**: Returns the average value of a numeric column.

  **Example**: To find the average price of products in the `products` table:
  ```sql
  SELECT AVG(price) FROM products;
  ```

- **MIN()**: Returns the smallest value in a column.

  **Example**: To find the minimum order amount from the `orders` table:
  ```sql
  SELECT MIN(order_amount) FROM orders;
  ```

- **MAX()**: Returns the largest value in a column.

  **Example**: To find the maximum price of products in the `products` table:
  ```sql
  SELECT MAX(price) FROM products;
  ```

#### GROUP BY and HAVING Clauses
The `GROUP BY` clause is used in conjunction with aggregate functions to group rows that have the same values in specified columns into summary rows. The `HAVING` clause is used to filter groups based on aggregate values.

- **GROUP BY**: This clause groups rows that share a common value in specified columns.

  **Example**: To count the number of orders for each customer:
  ```sql
  SELECT customer_id, COUNT(*) AS order_count
  FROM orders
  GROUP BY customer_id;
  ```

- **HAVING**: This clause is used to filter groups based on an aggregate condition. It is similar to the `WHERE` clause but is applied after the grouping has occurred.

  **Example**: To find customers who have placed more than 5 orders:
  ```sql
  SELECT customer_id, COUNT(*) AS order_count
  FROM orders
  GROUP BY customer_id
  HAVING COUNT(*) > 5;
  ```

### Summary
Using aggregate functions along with the `GROUP BY` and `HAVING` clauses allows you to summarize and analyze data effectively in SQL. By mastering these tools, you can gain valuable insights from your data, such as totals, averages, and counts, while also filtering results based on aggregate criteria. This is essential for reporting and data analysis in any database-driven application.