# PROCEDURE
In PostgreSQL, a stored `procedure` is a set of SQL statements that can be defined and stored in the database server. Stored procedures are often used to `encapsulate` a set of operations or business logic and can be invoked by name as a `single statement`.

Here's a basic structure of a stored procedure in PostgreSQL:

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

Let's break down the components of the stored procedure:

- `CREATE OR REPLACE PROCEDURE`: This statement is used to create or replace a stored procedure. If the procedure already exists, the `OR REPLACE` option will replace the existing procedure.

- `procedure_name`: This is the name of the stored procedure.

- `(parameter1 datatype, parameter2 datatype)`: These are input parameters that the procedure can accept. You can define multiple parameters as needed.

- `LANGUAGE plpgsql`: Specifies the procedural language to be used. In this example, `plpgsql` is used, which is a procedural language for PostgreSQL.

- `AS $$ ... $$`: The procedural code block enclosed between `$$` symbols. This is where you write your SQL statements and procedural logic.

- `BEGIN ... END;`: The block that contains the procedural logic. You can include multiple SQL statements and procedural code within this block.

- Example SQL statement: In the example, an `INSERT INTO` statement is used to insert data into a table.

After creating a stored procedure, you can execute it by calling its name with the provided parameters:

```sql
CALL procedure_name(parameter1_value, parameter2_value);
```

Stored procedures in PostgreSQL provide a way to encapsulate and reuse complex logic, enhance security, and improve performance by reducing the amount of data transferred between the client and the server.
