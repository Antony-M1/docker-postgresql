# Views
In PostgreSQL, a view is a `virtual table` that is based on the result of a `SELECT` query. A view allows you to `encapsulate` complex queries and present the result as if it were a table. Views can be used to simplify `queries`, provide an additional layer of security, and modularize complex SQL logic

## Create View
**Syntax to create a view**

```
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```
**Example**
```
CREATE VIEW employee_view AS
SELECT employee_id, first_name, last_name
FROM employees
WHERE department = 'IT';

```
In this example, a view named `employee_view` is created based on the `employees` table. The view includes only the columns `employee_id`, `first_name`, and `last_name` for employees in the `IT` department.

## How To Use Views?
Once a view is created, you can query it like a regular table:
```
SELECT * FROM employee_view;
```

It's important to note that a view doesn't store data `itself`; it's a `saved query` that is executed `dynamically` when queried. If the underlying tables change, the view reflects those changes automatically.

### Update View
To update an existing view, you can use the `CREATE OR REPLACE VIEW` syntax:
```
CREATE OR REPLACE VIEW employee_view AS
SELECT employee_id, first_name, last_name
FROM employees
WHERE department = 'Finance';
```
This statement modifies the existing `employee_view` to include employees from the `Finance` department.

Remember to tailor the view definition to your specific use case and requirements.

# Questions
### Can I use the table name as view name?
No. it will be through error. I won't allow you to create view like that.

If you have a table named `customer_details` and you're attempting to create a view with the same name (`customer_details`), you might encounter an error because PostgreSQL does not allow creating a view with the same name as an existing table in the same schema. The names of tables and views must be unique within a schema.

**Query**
```
CREATE VIEW actor AS
    SELECT * FROM customer_details;
```
**Error**
```
[42P07] ERROR: relation "customer_details" already exists
```

# Naming conventional
Choosing meaningful and clear names for views is essential for maintaining a well-organized and understandable database schema. Here are some suggestions for naming views:

1. **Use Descriptive Names:**
   - Choose names that clearly convey the purpose or content of the view.
   - Avoid generic names like "view1" or "temp_view."

2. **Include Keywords:**
   - Consider including keywords like "view" or "vw" as a prefix to explicitly indicate that it's a view.

3. **Include Source Table Names:**
   - If the view is based on specific tables, consider including the names of those tables in the view name.
   - Example: `customer_orders_summary_view`

4. **Avoid Ambiguity:**
   - Ensure that the view name doesn't create confusion with existing table names or other views.
   - Make it clear that it's a view and not a base table.

5. **Follow a Naming Convention:**
   - Adopt a consistent naming convention across your database, so it's easy to understand the purpose of different database objects.
   - Example: `vw_[ObjectName]` or `[SchemaName].[vw_ObjectName]`

6. **Be Concise but Informative:**
   - Keep the name concise while providing enough information about the view's content or purpose.

7. **Consider CamelCase or Underscores:**
   - Choose a naming style that aligns with your organization's conventions. CamelCase (e.g., `customerOrdersSummaryView`) or underscores (e.g., `customer_orders_summary_view`) are common styles.

8. **Avoid Special Characters:**
   - Stick to alphanumeric characters and underscores to ensure compatibility and ease of use.

Example:
```sql
-- Naming Example: vw_CustomerOrdersSummary
CREATE VIEW vw_CustomerOrdersSummary AS
SELECT customer_id, COUNT(order_id) AS order_count
FROM customer_orders
GROUP BY customer_id;
```

Remember that the key is to make the names both informative and consistent. This makes it easier for developers, administrators, and other stakeholders to understand the purpose of the views within your database schema.
