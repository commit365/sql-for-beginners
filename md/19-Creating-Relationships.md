### Lesson 19: Creating Relationships

#### Defining Primary and Foreign Keys
In relational databases, relationships between tables are established using keys. 

- **Primary Key**: A primary key is a unique identifier for each record in a table. It ensures that no two rows have the same value for this column and cannot contain NULL values. Each table should have a primary key to maintain data integrity.

  **Example**: In a `customers` table, the `customer_id` column can serve as the primary key:
  ```sql
  CREATE TABLE customers (
      customer_id INT PRIMARY KEY,
      name VARCHAR(50),
      email VARCHAR(100)
  );
  ```

- **Foreign Key**: A foreign key is a column (or a set of columns) in one table that refers to the primary key in another table. It establishes a link between the two tables, enforcing referential integrity.

  **Example**: In an `orders` table, the `customer_id` column can be a foreign key that references the `customer_id` in the `customers` table:
  ```sql
  CREATE TABLE orders (
      order_id INT PRIMARY KEY,
      customer_id INT,
      order_date DATE,
      FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
  );
  ```

#### One-to-One, One-to-Many, and Many-to-Many Relationships
Understanding the types of relationships between tables is crucial for effective database design:

- **One-to-One Relationship**: In a one-to-one relationship, a record in Table A is associated with exactly one record in Table B, and vice versa. This type of relationship is less common but can be useful for separating data.

  **Example**: A `users` table and a `user_profiles` table where each user has one profile:
  ```sql
  CREATE TABLE users (
      user_id INT PRIMARY KEY,
      username VARCHAR(50)
  );

  CREATE TABLE user_profiles (
      profile_id INT PRIMARY KEY,
      user_id INT UNIQUE,
      bio TEXT,
      FOREIGN KEY (user_id) REFERENCES users(user_id)
  );
  ```

- **One-to-Many Relationship**: In a one-to-many relationship, a record in Table A can be associated with multiple records in Table B, but a record in Table B is associated with only one record in Table A. This is the most common type of relationship.

  **Example**: A `customers` table and an `orders` table where each customer can have multiple orders:
  ```sql
  CREATE TABLE customers (
      customer_id INT PRIMARY KEY,
      name VARCHAR(50)
  );

  CREATE TABLE orders (
      order_id INT PRIMARY KEY,
      customer_id INT,
      order_date DATE,
      FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
  );
  ```

- **Many-to-Many Relationship**: In a many-to-many relationship, records in Table A can be associated with multiple records in Table B, and records in Table B can be associated with multiple records in Table A. This relationship is implemented using a junction table.

#### Using Junction Tables for Many-to-Many Relationships
A junction table (or associative table) is used to establish a many-to-many relationship between two tables. This table typically contains foreign keys that reference the primary keys of the two related tables.

**Example**: Consider a scenario where students can enroll in multiple courses, and each course can have multiple students:

1. **Students Table**:
   ```sql
   CREATE TABLE students (
       student_id INT PRIMARY KEY,
       name VARCHAR(50)
   );
   ```

2. **Courses Table**:
   ```sql
   CREATE TABLE courses (
       course_id INT PRIMARY KEY,
       course_name VARCHAR(100)
   );
   ```

3. **Enrollment Table (Junction Table)**:
   ```sql
   CREATE TABLE enrollment (
       student_id INT,
       course_id INT,
       PRIMARY KEY (student_id, course_id),
       FOREIGN KEY (student_id) REFERENCES students(student_id),
       FOREIGN KEY (course_id) REFERENCES courses(course_id)
   );
   ```

In this example, the `enrollment` table allows you to track which students are enrolled in which courses, creating a many-to-many relationship between students and courses.

### Summary
Creating relationships in a relational database is fundamental for maintaining data integrity and enabling efficient data retrieval. By defining primary and foreign keys, understanding different types of relationships (one-to-one, one-to-many, and many-to-many), and using junction tables for many-to-many relationships, you can design a well-structured database that effectively models real-world scenarios. This knowledge is essential for building robust and scalable database applications.