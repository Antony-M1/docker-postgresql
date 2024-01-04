# PROCEDURE
In PostgreSQL, a stored `procedure` is a set of SQL statements that can be defined and stored in the database server. Stored procedures are often used to `encapsulate` a set of operations or business logic and can be invoked by name as a `single statement`.

### Basic structure of a stored procedure
```sql
CREATE OR REPLACE PROCEDURE procedure_name(parameter1 datatype, parameter2 datatype)
LANGUAGE plpgsql
AS $$
BEGIN
  -- SQL statements and procedural logic go here
  -- You can use the provided parameters as well
  
  -- Example: Inserting data into a table
  INSERT INTO your_table (column1, column2) VALUES (parameter1, parameter2);

  -- Additional logic...

END;
$$;

```
