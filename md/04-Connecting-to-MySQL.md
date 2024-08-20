### Lesson 4: Connecting to MySQL

#### Using MySQL Workbench
MySQL Workbench is a powerful graphical user interface (GUI) tool that allows you to manage MySQL databases easily. Here’s how to connect to a MySQL database using MySQL Workbench:

1. **Open MySQL Workbench**: Launch the MySQL Workbench application on your computer.

2. **Create a New Connection**:
   - Click on the "+" icon next to "MySQL Connections" on the main screen.
   - In the "Setup New Connection" window, enter a name for your connection (e.g., "Local MySQL").

3. **Enter Connection Details**:
   - **Hostname**: Enter `localhost` if you are connecting to a local MySQL server. For remote servers, enter the server's IP address or hostname.
   - **Port**: The default MySQL port is `3306`. Change it only if your server uses a different port.
   - **Username**: Enter your MySQL username (e.g., `root`).
   - **Password**: Click on the "Store in Vault" button (or "Store in Keychain" on macOS) to enter your password securely.

4. **Test the Connection**: Click the "Test Connection" button to verify that the connection details are correct. If successful, you will see a confirmation message.

5. **Save and Connect**: Click "OK" to save the connection. You can now double-click on the connection name to connect to the MySQL server.

6. **Using MySQL Workbench**: Once connected, you can use the SQL Editor to run queries, manage databases, and perform various administrative tasks.

#### Command-Line Interface Basics
The MySQL command-line interface (CLI) is a powerful tool for interacting with MySQL databases directly through text commands. Here’s how to connect to MySQL using the command line:

1. **Open the Command Line**:
   - On Windows, open the Command Prompt.
   - On macOS or Linux, open the Terminal.

2. **Connect to MySQL**:
   - Type the following command to connect to the MySQL server:
     ```bash
     mysql -u username -p
     ```
   - Replace `username` with your MySQL username (e.g., `root`). The `-p` flag prompts you to enter your password.

3. **Enter Your Password**: After pressing Enter, you will be prompted to enter your password. Type your password and press Enter. Note that the password will not be visible as you type.

4. **Accessing the MySQL Shell**: If the connection is successful, you will see the MySQL prompt, which looks like this:
   ```bash
   mysql>
   ```

5. **Basic Commands**:
   - To show all databases:
     ```sql
     SHOW DATABASES;
     ```
   - To use a specific database:
     ```sql
     USE database_name;
     ```
   - To show tables in the current database:
     ```sql
     SHOW TABLES;
     ```
   - To exit the MySQL shell, type:
     ```sql
     EXIT;
     ```

Using the command-line interface can be faster and more efficient for executing SQL commands, especially for advanced users. It’s a valuable skill to develop alongside using graphical tools like MySQL Workbench.