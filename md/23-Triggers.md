### Lesson 23: Triggers

#### What are Triggers?
Triggers are special types of stored procedures that automatically execute (or "fire") in response to specific events on a particular table in a database. These events can include actions such as `INSERT`, `UPDATE`, or `DELETE`. Triggers help maintain data integrity, enforce business rules, and automate certain tasks without requiring explicit calls from applications.

**Key Characteristics of Triggers**:
- **Automatic Execution**: Triggers are invoked automatically when a specified event occurs.
- **Event-Driven**: They are tied to specific events (e.g., row-level changes) and can be defined to execute before or after the event.
- **No Direct Invocation**: Unlike stored procedures, triggers cannot be called directly; they are triggered by the database engine.

#### Creating and Managing Triggers
To create a trigger, you use the `CREATE TRIGGER` statement. The basic syntax is as follows:

```sql
CREATE TRIGGER trigger_name
{BEFORE | AFTER} {INSERT | UPDATE | DELETE}
ON table_name
FOR EACH ROW
BEGIN
    -- SQL statements
END;
```

- **trigger_name**: The name of the trigger.
- **BEFORE | AFTER**: Specifies whether the trigger should execute before or after the event.
- **INSERT | UPDATE | DELETE**: Specifies the event that will trigger the execution.
- **table_name**: The name of the table on which the trigger is defined.
- **FOR EACH ROW**: Indicates that the trigger will execute for each row affected by the event.

**Example**: Creating a trigger that logs changes to the `orders` table whenever an order is updated:

```sql
CREATE TRIGGER log_order_update
AFTER UPDATE ON orders
FOR EACH ROW
BEGIN
    INSERT INTO order_log (order_id, old_status, new_status, change_date)
    VALUES (OLD.order_id, OLD.status, NEW.status, NOW());
END;
```

In this example, the trigger logs the old and new status of an order into an `order_log` table whenever an order is updated.

#### Use Cases for Triggers
Triggers can be used in various scenarios to enhance database functionality. Here are some common use cases:

1. **Auditing Changes**: Triggers can be used to automatically log changes made to a table, capturing who made the change and when it occurred. This is useful for maintaining an audit trail.

2. **Enforcing Business Rules**: Triggers can enforce business rules by preventing certain actions. For example, a trigger can prevent the deletion of a record if it is referenced in another table.

3. **Maintaining Data Integrity**: Triggers can help maintain data integrity by automatically updating related tables or fields when a change occurs. For example, if a customer's status changes, a trigger can automatically update the status of all their related orders.

4. **Calculating Derived Values**: Triggers can be used to automatically calculate and update derived values based on changes in the data. For instance, updating a total sales amount whenever a new sale is recorded.

5. **Sending Notifications**: Triggers can be set up to send notifications or alerts when certain conditions are met, such as when inventory levels fall below a specified threshold.

### Summary
Triggers are powerful database objects that allow you to automate actions in response to specific events. By understanding how to create and manage triggers, as well as their various use cases, you can enhance the functionality of your database and ensure data integrity. Triggers help enforce business rules, maintain audit trails, and automate tasks, making them a valuable tool in database management.