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
