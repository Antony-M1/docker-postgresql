# Funtions

While stored procedures and functions in PostgreSQL share similarities, they serve slightly different purposes and have some key distinctions:

1. **Stored Procedures:**
   - Procedures in PostgreSQL are typically used for procedural programming and can perform a series of SQL and procedural language statements.
   - They are defined using the `CREATE PROCEDURE` statement.
   - Procedures can have input and output parameters, but they do `not necessarily return a value`.
   - Execution of a procedure is usually done with the `CALL` statement.

   Example of a stored procedure:

   ```sql
   CREATE OR REPLACE PROCEDURE my_procedure(param1 INT, param2 VARCHAR)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

2. **Functions:**
   - Functions, on the other hand, are used to encapsulate and return a single value or a table.
   - They are defined using the `CREATE FUNCTION` statement.
   - Functions can have input parameters and may return a value using the `RETURNS` clause.
   - Execution of a function is typically done by calling it in an SQL query.

   Example of a function:

   ```sql
   CREATE OR REPLACE FUNCTION my_function(param1 INT, param2 VARCHAR)
   RETURNS INT  -- Example of a function returning an integer
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Function logic...
     RETURN 42; -- Example return statement
   END;
   $$;
   ```

In summary, while both stored procedures and functions allow you to define custom routines in PostgreSQL, procedures are often used for procedural logic without necessarily returning a value, while functions are designed to return a value. The choice between using a procedure or a function depends on the specific requirements of your application and the nature of the task you are performing.
