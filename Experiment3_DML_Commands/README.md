## Name: Yuvan M
## RegNo: 212223240188
# Experiment 3: DML Commands


## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
--Write a SQL statement to update the product_name as 'Grapefruit' whose product_id is 4 in the products table.
```sql
-- update products
set product_name='Grapefruit'
where product_id=4;
```

**Output:**
![image](https://github.com/user-attachments/assets/af3f6830-d5ff-4078-897b-34d97dae852e)



**Question 2**
---
-- Write a SQL query to reduce the reorder level by 30% where cost price is more than 50 and quantity in stock is less than 100 in the products table.

```sql
-- --update Products
set reorder_lvl=reorder_lvl*0.7
where cost_price>50 and quantity<100;
```

**Output:**

![image](https://github.com/user-attachments/assets/0c0ad3bd-a791-4127-909e-a301d155ce49)


**Question 3**
---
--Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

```sql
--delete from Surgeries 
where surgery_date='2024-02-28';
```

**Output:**

![image](https://github.com/user-attachments/assets/60fcabb2-3739-4561-8abd-f717550aac2f)


**Question 4**
---
-- Write a SQL query to Delete customers from 'customer' table where 'GRADE' is not equal to 3.

```sql
--delete from customer
where GRADE!=3;
```

**Output:**
![image](https://github.com/user-attachments/assets/244dd449-0bbe-4c6b-943a-9d339c7632d5)


**Question 5**
---
--Write a query to fetch details of employees whose EmpLname ends with an alphabet ‘A’ and contains five alphabets.

```sql
-- select * from EmployeeInfo 
where EmpLname like '%A' and length(EmpLname)=5;
```

**Output:**

![image](https://github.com/user-attachments/assets/7ce63721-1491-42ee-9298-802d3026d5e7)


**Question 6**
---
-- Write a SQL query to classify base in the Calculations table as 'Provided' if it is not NULL, otherwise 'Not Provided'.

```sql
-- select id,base,
case when base is not NULL then 'Provided'
else 'Not Provided'
end as base_status
from Calculations;
```

**Output:**
![image](https://github.com/user-attachments/assets/b9c54104-cb6c-40f4-b090-ebb5b04687b8)


**Question 7**
---
--Write a SQL query to calculate the final price after applying both the discount and the tax. Return product_id, original_price, discount_percentage, tax_rate, and final_price.

```sql
-- select product_id,original_price,discount_percentage,tax_rate,(original_price*(1-discount_percentage))*(1+tax_rate) as final_price
from products;
```

**Output:**

![image](https://github.com/user-attachments/assets/7efe26fd-b7fe-4bca-94e6-708d34c09749)


**Question 8**
---
-- Create a report that shows the capitalized FirstName and capitalized LastName renamed as FirstName and Lastname respectively and EmployeeId from the employees table sorted by EmployeeId in descending order.

```sql
-- select upper(FirstName) AS FirstName,upper(LastName) AS LastName,EmployeeId
from employees
order by EmployeeID desc;
```

**Output:**

![image](https://github.com/user-attachments/assets/51ad474f-3b09-44c9-8d92-5fe82f23bb67)


**Question 9**
---
--Write a SQL statement to retrieve city(column name) of all customers from customers table without any repeats.

```sql
--select distinct city from customers;
```

**Output:**

![image](https://github.com/user-attachments/assets/7abc7d03-9808-4656-a956-91d80746ea21)


**Question 10**
---
-- Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'

```sql
-- update EMPLOYEES
SET SALARY= SALARY *2
WHERE JOB_ID like'%MAN';
```

**Output:**

![image](https://github.com/user-attachments/assets/27296535-166f-4e78-88de-c2be23f97ae9)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
