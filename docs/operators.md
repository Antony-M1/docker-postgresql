# Arithmatic Operators
In PostgreSQL, arithmetic operators are used for performing mathematical operations on numeric data types. Here are the commonly used arithmetic operators:

1. **Addition (`+`):**
   - Adds two numbers.
   - Example: `SELECT 10 + 5;`

2. **Subtraction (`-`):**
   - Subtracts the right operand from the left operand.
   - Example: `SELECT 10 - 5;`

3. **Multiplication (`*`):**
   - Multiplies two numbers.
   - Example: `SELECT 10 * 5;`

4. **Division (`/`):**
   - Divides the left operand by the right operand.
   - Example: `SELECT 10 / 5;`

5. **Modulus (`%`):**
   - Returns the remainder of the division of the left operand by the right operand.
   - Example: `SELECT 10 % 3;` (returns 1, as 10 divided by 3 leaves a remainder of 1)

6. **Exponentiation (`^` or `**`):**
   - Raises the left operand to the power of the right operand.
   - Example: `SELECT 2 ^ 3;` or `SELECT 2 ** 3;` (both return 8)

7. **Unary Plus (`+`):**
   - Represents a positive number. It is often used for clarity and is optional.
   - Example: `SELECT +5;`

8. **Unary Minus (`-`):**
   - Represents a negative number or negates the value of the operand.
   - Example: `SELECT -5;`

These operators can be used in combination with numeric literals, columns, or expressions to perform arithmetic calculations in SQL queries. It's important to consider the data types involved in the operations to ensure correct results and avoid unexpected behavior.


# Logical Operators
In PostgreSQL, logical operators are used to perform logical operations on Boolean expressions or conditions. Here are the commonly used logical operators:

1. **AND (`AND` or `&&`):**
   - The `AND` operator returns true if both conditions on its left and right sides are true.
   - Example: `SELECT (5 > 3) AND (10 < 15);` (returns true)

2. **OR (`OR` or `||`):**
   - The `OR` operator returns true if at least one of the conditions on its left or right side is true.
   - Example: `SELECT (5 > 3) OR (10 > 15);` (returns true)

3. **NOT (`NOT` or `!`):**
   - The `NOT` operator negates the result of a Boolean expression. If the expression is true, `NOT` makes it false, and if the expression is false, `NOT` makes it true.
   - Example: `SELECT NOT (5 > 3);` (returns false)

4. **IN (`IN`):**
   - The `IN` operator checks whether a value matches any value in a list of values or a subquery result.
   - Example: `SELECT column_name FROM table_name WHERE column_name IN (value1, value2, ...);`

5. **BETWEEN (`BETWEEN`):**
   - The `BETWEEN` operator checks whether a value is within a specified range (inclusive).
   - Example: `SELECT column_name FROM table_name WHERE column_name BETWEEN value1 AND value2;`

6. **LIKE (`LIKE`):**
   - The `LIKE` operator is used for pattern matching in string comparisons. It allows the use of wildcard characters such as `%` (matches any sequence of characters) and `_` (matches any single character).
   - Example: `SELECT column_name FROM table_name WHERE column_name LIKE 'pattern';`

7. **IS NULL (`IS NULL`):**
   - The `IS NULL` operator is used to check if a value is `NULL`.
   - Example: `SELECT column_name FROM table_name WHERE column_name IS NULL;`

8. **IS NOT NULL (`IS NOT NULL`):**
   - The `IS NOT NULL` operator is used to check if a value is not `NULL`.
   - Example: `SELECT column_name FROM table_name WHERE column_name IS NOT NULL;`

These logical operators are essential for constructing complex queries and filtering data based on specified conditions.
