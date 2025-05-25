# Experiment 9: PL/SQL – Procedures and Functions

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
### Program:
![image](https://github.com/user-attachments/assets/38cbb4fb-77ec-4b75-b034-f024d3917b53)

**Expected Output:**  
Square of 6 is 36

### Output:
![image](https://github.com/user-attachments/assets/f7de8e73-94a3-41ba-bf01-3e103058b7ef)

---

## 2. Write a PL/SQL Function to Return the Factorial of a Number

### Steps:
- Create a function named `get_factorial`.
- Declare a parameter to accept a number.
- Use a loop to calculate the factorial.
- Return the result using the `RETURN` statement.
- Call the function using a `SELECT` statement or in an anonymous block.

### Program
![image](https://github.com/user-attachments/assets/0a7bed5d-1096-4c8e-ac34-d48f7bdf6f0d)

**Expected Output:**  
Factorial of 5 is 120

### Output:
![image](https://github.com/user-attachments/assets/ad3314bb-2cb1-4a39-9cce-fa4dbaea8d9e)

---

## 3. Write a PL/SQL Procedure to Check Whether a Number is Even or Odd

### Steps:
- Create a procedure named `check_even_odd`.
- Accept an input parameter.
- Use the `MOD` function to check if the number is divisible by 2.
- Display whether it is Even or Odd using `DBMS_OUTPUT.PUT_LINE`.

### Program:
![image](https://github.com/user-attachments/assets/017f9782-197a-4cf4-b698-45fe8514e49e)

**Expected Output:**  
12 is Even
### Output:
![image](https://github.com/user-attachments/assets/2fbc24fc-016e-4055-9be3-f3c34f13f279)

---

## 4. Write a PL/SQL Function to Return the Reverse of a Number

### Steps:
- Create a function named `reverse_number`.
- Accept an input number as parameter.
- Use a loop to reverse the digits of the number.
- Return the reversed number.
- Call the function and display the output.

### Program:
![image](https://github.com/user-attachments/assets/84aace0d-de26-4b88-9058-9219d185923a)

**Expected Output:**  
Reversed number of 1234 is 4321

### Output:
![image](https://github.com/user-attachments/assets/716fa3aa-ee9f-4d3e-a41d-cfce693d0e05)

---

## 5. Write a PL/SQL Procedure to Display the Multiplication Table of a Number

### Steps:
- Create a procedure named `print_table`.
- Accept an input number.
- Use a loop from 1 to 10 to multiply the input number.
- Display the multiplication results using `DBMS_OUTPUT.PUT_LINE`.

### Program:
![image](https://github.com/user-attachments/assets/6d504db2-8fcc-4106-83ae-2f7726d10ec7)

**Expected Output:**  
Multiplication table of 5:  
5 x 1 = 5  
5 x 2 = 10  
5 x 3 = 15  
...  
5 x 10 = 50

### Output:
![image](https://github.com/user-attachments/assets/e2f1b90b-237e-47ce-b2d2-8e4dd39f31c3)

## RESULT
Thus, the PL/SQL programs using procedures and functions were written, compiled, and executed successfully.
