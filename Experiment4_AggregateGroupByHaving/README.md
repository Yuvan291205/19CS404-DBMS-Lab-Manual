## Name: Yuvan M
## RegNo: 212223240188

# Experiment 4: Aggregate Functions, Group By and Having Clause

## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
-- How many prescriptions were written by each doctor?

```sql
--SELECT DoctorID, COUNT(*)AS
TotalPrescriptions
FROM Prescriptions
GROUP BY DoctorID;
```

**Output:**

![image](https://github.com/user-attachments/assets/6925daf6-3609-4b29-bcdd-4dfac43dc2b1)


**Question 2**
---
-- How many patients are covered by each insurance company?

```sql
-- SELECT InsuranceCompany,
COUNT ( DISTINCT PatientID )AS
TotalPatients
FROM Insurance
GROUP BY InsuranceCompany;
```

**Output:**
![image](https://github.com/user-attachments/assets/08de6838-55c5-478c-9e96-d80b65fb70b9)

**Question 3**
---
-- How many patients are there in each city?

```sql
-- SELECT Address, COUNT(*)AS
TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

![image](https://github.com/user-attachments/assets/a0a25d1c-7460-461c-b9fb-ff8fe10ed96e)


**Question 4**
---
--Write a SQL query to find the minimum purchase amount.

```sql
-- SELECT MIN(purch_amt)AS
MINIMUM
FROM orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/2bea4213-0321-4c67-bd35-8535c89128ff)


**Question 5**
---
-- Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

```sql
-- SELECT COUNT(*)AS 
COUNT
FROM customer
WHERE city!='Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/a8665da0-56e2-4771-bb60-0e814b469831)


**Question 6**
---
-- Write a SQL query to find the maximum purchase amount.

```sql
-- SELECT MAX (purch_amt)AS MAXIMUM
FROM orders;
```

**Output:**

![image](https://github.com/user-attachments/assets/a49915a5-83bc-4ead-8ddb-c11e13109961)

**Question 7**
---
-- Write a SQL query to Calculate the average email length (in characters) for people who lives in Mumbai city

```sql
-- SELECT AVG(LENGTH(email))AS
avg_email_length_below_30
FROM customer
WHERE city='Mumbai';
```

**Output:**

![image](https://github.com/user-attachments/assets/ba86fc59-5c13-4036-8df7-5b41a5ca5246)


**Question 8**
---
--Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the average age for each group, and excludes groups where the average age is not less than 24.

```sql
--SELECT
  (age/5)*5 AS age_group ,
   AVG(age)
FROM customer1
GROUP BY age_group 
HAVING AVG(age)<24;
```

**Output:**
![image](https://github.com/user-attachments/assets/e84a06fa-049a-48b5-8084-b60675836410)


**Question 9**
---
-- Write the SQL query that achieves the selection of category and calculates the sum of the product of price and category ID as Revenue for each category from the "products" table, and includes only those products where the total revenue is greater than 25.

```sql
-- SELECT CATEGORY_ID, SUM(price*category_id) AS Revenue
FROM products
GROUP BY category_id
HAVING SUM(price *category_id)>25;
```

**Output:**
![image](https://github.com/user-attachments/assets/933fbf78-c97a-43ca-ad46-aba8c69d5031)


**Question 10**
---
-- How many medical records are there for each patient?

```sql
-- select PatientID, count(RecordID) as 'TotalRecords'
from MedicalRecords
group by PatientID;
```

**Output:**
![image](https://github.com/user-attachments/assets/686c0ab6-6c07-4ad0-8037-d13d65f1d199)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
