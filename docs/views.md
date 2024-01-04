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

