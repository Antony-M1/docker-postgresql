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


# Questions
### Can I use the table name as PROCEDURE name ?
In PostgreSQL, the naming conventions for `stored procedures` and `tables` are different. While it is technically `possible` to name a stored procedure with the same name as a table, it's `generally not recommended` to do so for clarity and `maintainability` reasons.

It's common practice to use meaningful names that convey the purpose of the stored procedure. Naming stored procedures after tables may lead to confusion and make it harder for developers (including yourself) to understand the purpose of each object in the database.

Here's an example of a more meaningful naming convention for a stored procedure:

```sql
CREATE OR REPLACE PROCEDURE insert_data_into_example_table(param1 INT, param2 VARCHAR)
LANGUAGE plpgsql
AS $$
BEGIN
  -- Example: Inserting data into a table named example_table
  INSERT INTO example_table (column1, column2) VALUES (param1, param2);

  -- Additional logic...

END;
$$;
```

In the example above, the stored procedure is named `insert_data_into_example_table`, which clearly indicates its purpose.

Using meaningful and descriptive names for stored procedures helps improve code readability and maintainability. It's a good practice to choose names that reflect the functionality or operation performed by the stored procedure rather than naming it after a table.

# Naming Conventional
When naming stored procedures in PostgreSQL, it's a good practice to follow a consistent and meaningful naming convention that reflects the purpose and functionality of the procedure. While naming conventions can vary, here are some common practices that can help improve clarity and maintainability:

1. **Use Descriptive Names:**
   - Choose names that clearly convey the purpose or action performed by the stored procedure.
   - Avoid generic or ambiguous names.

   ```sql
   -- Example: Descriptive name for a procedure inserting user data
   CREATE OR REPLACE PROCEDURE insert_user_data(user_id INT, username VARCHAR)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

2. **Use CamelCase or Underscore Notation:**
   - Choose a consistent casing convention, such as CamelCase or underscore_notation.
   - Stick to the chosen convention for consistency across procedures.

   ```sql
   -- Example: CamelCase
   CREATE OR REPLACE PROCEDURE processCustomerOrder(order_id INT)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;

   -- Example: Underscore Notation
   CREATE OR REPLACE PROCEDURE process_customer_order(order_id INT)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

3. **Include Object Type Prefix:**
   - Prefix the procedure name with an abbreviation indicating the type of object (e.g., `sp_` for stored procedure).

   ```sql
   -- Example: Prefix with "sp_"
   CREATE OR REPLACE PROCEDURE sp_insert_user_data(user_id INT, username VARCHAR)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

4. **Avoid Reserved Words:**
   - Avoid using PostgreSQL reserved words as procedure names to prevent conflicts.

   ```sql
   -- Example: Avoid using reserved words
   CREATE OR REPLACE PROCEDURE process_order(order_id INT)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

5. **Be Consistent:**
   - Establish a consistent naming convention across your database objects.
   - Consider documenting your naming conventions for the development team.

   ```sql
   -- Example: Consistent naming convention
   CREATE OR REPLACE PROCEDURE sp_update_customer_address(customer_id INT, new_address VARCHAR)
   LANGUAGE plpgsql
   AS $$
   BEGIN
     -- Procedure logic...
   END;
   $$;
   ```

Ultimately, the goal is to choose a naming convention that makes your code easy to read, understand, and maintain. Consistency is key, so stick to your chosen convention across all stored procedures in your database.
