# Experiment 2: DDL Commands

## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1
--
-- Create a table named Shipments with the following constraints:

    ShipmentID as INTEGER should be the primary key.
    ShipmentDate as DATE.
    SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).
    OrderID as INTEGER should be a foreign key referencing Orders(OrderID).

```sql
---CREATE TABLE Shipments
(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY(OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**
![image](https://github.com/user-attachments/assets/37c7b4c7-20e0-41af-959d-3a3f55c64fcc)



**Question 2**
---
-- Insert the following customers into the Customers table:

CustomerID Name Address City ZipCode



```sql
-- INSERT INTO Customers (CustomerID,Name,Address,City,ZipCode)
VALUES
(302,'Laura Croft','456 Elm St','Seattle',98101),
(303,'Bruce Wayne','789 Oak St','Gotham',10001);
```

**Output:**

![image](https://github.com/user-attachments/assets/dbcae597-9fe0-4a55-80af-387facb66eb2)


**Question 3**
---
-- Write a SQL query to add a column named Date_of_birth as Date in the Student_details table.

```sql
--  ALTER TABLE Student_details
ADD COLUMN Date_of_birth Date;
```

**Output:**

![image](https://github.com/user-attachments/assets/d83340ae-86cd-43a3-88bd-a985dacd31d2)


**Question 4**
---
-- -- Insert all customers from Old_customers into Customers

Table attributes are CustomerID, Name, Address, Email

```sql
-- --INSERT INTO Customers (CustomerID, Name, Address, Email)
SELECT CustomerID, Name, Address, Email FROM Old_customers;
```

**Output:**

![image](https://github.com/user-attachments/assets/1fef5b6d-0500-4805-9fb0-4cdc938ae8b4)


**Question 5**
---
-- Write an SQL command can to add a column named email of type TEXT to the customers table

```sql
-- Write an SQL command can to add a column named email of type TEXT to the customers table
```

**Output:**

![image](https://github.com/user-attachments/assets/77edd6de-635a-4d0f-9891-fd7554cc4c63)


**Question 6**
---
-- Create a table named Invoices with the following constraints:

```sql
-- InvoiceID as INTEGER should be the primary key.
InvoiceDate as DATE.
Amount as REAL should be greater than 0.
DueDate as DATE should be greater than the InvoiceDate.
OrderID as INTEGER should be a foreign key referencing Orders(OrderID).
```

**Output:**
![image](https://github.com/user-attachments/assets/e0651312-8a37-4a8e-9133-9800ecc24525)


**Question 7**
---
-- --Insert the below data into the Books table, allowing the Publisher and Year columns to take their default values.

ISBN Title Author

```sql
--INSERT INTO Books(ISBN,Title,Author)
VALUES('978-6655443321','Big Data Analytics','Karen Adams');
```

**Output:**

![image](https://github.com/user-attachments/assets/519ce060-d544-4c34-80a4-82d556fbf6fb)


**Question 8**
---
--  Create a new table named products with the following specifications:

```sql
--product_id as INTEGER and primary key.
product_name as TEXT and not NULL.
list_price as DECIMAL (10, 2) and not NULL.
discount as DECIMAL (10, 2) with a default value of 0 and not NULL.
A CHECK constraint at the table level to ensure:
    list_price is greater than or equal to discount
    discount is greater than or equal to 0
    list_price is greater than or equal to 0
```

**Output:**

![image](https://github.com/user-attachments/assets/cef8f9f0-d2ea-41bd-8134-31c10956b23f)


**Question 9**
---
-- Create a table named Events with the following columns:

```sql
-- -- CREATE TABLE Events
(
EventID INTEGER,
EventName TEXT,
EventDate DATE
);
```

**Output:**
![image](https://github.com/user-attachments/assets/9a06168c-47fd-477e-b230-d3c60a38514d)


**Question 10**
---
-- AttendanceID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
AttendanceDate as DATE.
Status as TEXT should be one of 'Present', 'Absent', 'Leave'.

```sql
-- --CREATE TABLE Attendance
(
 AttendanceID INTEGER primary key,
 EmployeeID INTEGER,
 AttendanceDate DATE,
 Status TEXT CHECK(Status IN('Present','Absent','Leave')),
 FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID)
);
```

**Output:**

![image](https://github.com/user-attachments/assets/56f7cf27-4630-41b9-973f-07463dd4627e)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
