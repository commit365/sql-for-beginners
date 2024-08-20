### Lesson 5: Creating Your First Database

#### Syntax for Creating a Database
Creating a database in MySQL is a straightforward process that involves using the `CREATE DATABASE` statement. The basic syntax is as follows:

```sql
CREATE DATABASE database_name;
```

- **database_name**: This is the name you want to give to your new database. It should be unique and follow the naming conventions (e.g., no spaces, special characters, or starting with a number).

#### Creating and Using a New Database
Follow these steps to create and use your first database in MySQL:

1. **Open MySQL Workbench or Command-Line Interface**:
   - If you're using MySQL Workbench, connect to your MySQL server.
   - If you're using the command-line interface, log in to MySQL using your credentials.

2. **Create a New Database**:
   - In the SQL Editor (MySQL Workbench) or at the MySQL prompt (CLI), enter the following command to create a new database. For example, let's create a database called `my_first_database`:
     ```sql
     CREATE DATABASE my_first_database;
     ```

3. **Verify Database Creation**:
   - To ensure that the database was created successfully, you can run the following command to list all databases:
     ```sql
     SHOW DATABASES;
     ```
   - You should see `my_first_database` listed among the databases.

4. **Using the New Database**:
   - To start using the newly created database, you need to select it with the `USE` statement:
     ```sql
     USE my_first_database;
     ```
   - After executing this command, any subsequent SQL commands (such as creating tables or inserting data) will be applied to `my_first_database`.

5. **Confirm the Current Database**:
   - You can confirm that you are using the correct database by running:
     ```sql
     SELECT DATABASE();
     ```
   - This command will return the name of the currently selected database.

6. **Next Steps**:
   - Now that you have created and selected your database, you can proceed to create tables, insert data, and perform other database operations.

By following these steps, you have successfully created your first database in MySQL and are ready to start working with it!