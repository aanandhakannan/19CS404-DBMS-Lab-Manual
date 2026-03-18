# Experiment 9: PL/SQL – Procedures and Functions

### NAME - AANANDHA KANNAN S

### REG NO - 212224040003

## AIM
To understand and implement procedures and functions in PL/SQL for performing various operations such as calculations, decision-making, and looping.

---

## THEORY

PL/SQL (Procedural Language/SQL) extends SQL by adding procedural constructs like variables, conditions, loops, procedures, and functions. Procedures and functions are subprograms that help modularize the code and improve reusability.

### **Procedure**
A PL/SQL **procedure** is a subprogram that performs a specific action. It does not return a value directly but can return values using `OUT` parameters.

**Syntax:**
```sql
CREATE OR REPLACE PROCEDURE procedure_name (parameters)
IS
BEGIN
   -- statements
END;
```

To call the procedure

```sql
EXEC procedure_name(arguments);
```

### **Function**
A PL/SQL **function** is a subprogram that returns a single value using the RETURN keyword.

```sql
CREATE OR REPLACE FUNCTION function_name (parameters)
RETURN datatype
IS
BEGIN
   -- statements
   RETURN value;
END;
```

To call the function:

```sql
SELECT function_name(arguments) FROM DUAL;
```

Key Differences:

-A procedure does not return a value, whereas a function must return a value.
-Functions can be called from SQL queries, procedures cannot (in most cases).

## 1. Write a PL/SQL Procedure to Find the Square of a Number

### Steps:
- Create a procedure named `find_square`.
- Declare a parameter to accept a number.
- Inside the procedure, compute the square of the input number.
- Use `DBMS_OUTPUT.PUT_LINE` to display the result.
- Call the procedure with a number as input.

**Expected Output:**  
Square of 6 is 36
### PROGRAM
```
CREATE OR REPLACE PROCEDURE find_square(n IN NUMBER)
IS
BEGIN
  DBMS_OUTPUT.PUT_LINE('Square of ' || n || ' is ' || (n * n));
END;
/

BEGIN
  find_square(6);
END;
/
```
### OUTPUT
<img width="512" height="205" alt="image" src="https://github.com/user-attachments/assets/a6eec574-c802-4dd1-a4f8-a17f8520ddf1" />


---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

**Expected Output:**  
Factorial of 5 is 120
### PROGRAM
```
CREATE OR REPLACE FUNCTION get_factorial(n IN NUMBER)
RETURN NUMBER
IS
  fact NUMBER := 1;
  i NUMBER := 1;
BEGIN
  WHILE i <= n LOOP
    fact := fact * i;
    i := i + 1;
  END LOOP;
  RETURN fact;
END;
/

BEGIN
  DBMS_OUTPUT.PUT_LINE('Factorial is: ' || get_factorial(5));
END;
/
```
### OUTPUT

<img width="470" height="142" alt="image" src="https://github.com/user-attachments/assets/73d17fd2-e5b3-4adc-a74d-b8fac8f88c22" />


---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
12 is Even

### PROGRAM
```
CREATE OR REPLACE PROCEDURE check_even_odd(n IN NUMBER)
IS
BEGIN
  IF MOD(n, 2) = 0 THEN
    DBMS_OUTPUT.PUT_LINE(n || ' is Even');
  ELSE
    DBMS_OUTPUT.PUT_LINE(n || ' is Odd');
  END IF;
END;
/

BEGIN
  check_even_odd(7);
END;
/
```
### OUTPUT

<img width="581" height="321" alt="image" src="https://github.com/user-attachments/assets/bece0854-0b66-4560-8bd5-0f227f248ec4" />


---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

**Expected Output:**  
Reversed number of 1234 is 4321

### PROGRAM
```
CREATE OR REPLACE FUNCTION reverse_number(n IN NUMBER)
RETURN NUMBER
IS
  num NUMBER := n;
  rev NUMBER := 0;
  rem NUMBER;
BEGIN
  WHILE num > 0 LOOP
    rem := MOD(num, 10);
    rev := rev * 10 + rem;
    num := TRUNC(num / 10);
  END LOOP;
  RETURN rev;
END;
/

BEGIN
  DBMS_OUTPUT.PUT_LINE('Reverse number is: ' || reverse_number(1535));
END;
/
```
### OUTPUT

<img width="744" height="405" alt="image" src="https://github.com/user-attachments/assets/4f2d7503-8fd5-4c00-a19c-faf3e93d8eb7" />


---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50
###
PROGRAM
```
CREATE OR REPLACE PROCEDURE print_table(n IN NUMBER)
IS
  i NUMBER := 1;
BEGIN
  DBMS_OUTPUT.PUT_LINE('Multiplication table of ' || n || ':');

  WHILE i <= 10 LOOP
    DBMS_OUTPUT.PUT_LINE(n || ' x ' || i || ' = ' || (n * i));
    i := i + 1;
  END LOOP;
END;
/

BEGIN
  print_table(5);
END;
/
```
### OUTPUT

<img width="543" height="271" alt="image" src="https://github.com/user-attachments/assets/13a0e8a1-a4b9-451b-a849-7580a006c5dc" />


## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
