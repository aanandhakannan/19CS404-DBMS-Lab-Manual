# Experiment 2: DDL Commands
### NAME - AANANDHA KANNAN S
### REG NO - 212224040003

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

**Question 1**
--
Create a table named Employees with the following constraints:



```sql
CREATE TABLE Employees(
EmployeeID INTEGER PRIMARY KEY,
FirstName TEXT NOT NULL,
LastName TEXT NOT NULL,
Email TEXT UNIQUE,
Salary INTEGER CHECK(Salary > 0),
DepartmentID INTEGER REFERENCES Departments(DepartmentID)
);

```

**Output:**

<img width="1252" height="338" alt="image" src="https://github.com/user-attachments/assets/b9299491-705a-4ebb-9646-d51746b0464e" />


**Question 2**
---
Insert the below data into the Student_details table, allowing the Subject and MARKS columns to take their default values.



```sql
INSERT INTO Student_details(RollNo,Name,Gender) VALUES(204,"Samuel Black","M");
```

**Output:**

<img width="941" height="244" alt="image" src="https://github.com/user-attachments/assets/2979322b-ee8f-4822-be2f-e1614bbd7f9d" />


**Question 3**
---
Create a table named Orders with the following constraints:


```sql
CREATE TABLE Orders(
OrderID INTEGER PRIMARY KEY,
OrderDate DATE NOT NULL,
CustomerID INTEGER REFERENCES Customers(CustomerID)
);
```

**Output:**

<img width="1330" height="250" alt="image" src="https://github.com/user-attachments/assets/760a85d6-07e8-4e9a-a3cf-52a7e9197c37" />


**Question 4**
---
Create a table named Bonuses with the following constraints:
BonusID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
BonusAmount as REAL should be greater than 0.
BonusDate as DATE.
Reason as TEXT should not be NULL.

```sql
CREATE TABLE Bonuses(
BonusID INTEGER PRIMARY KEY,
EmployeeID INTEGER REFERENCES Employees(EmployeeID),
BonusAmount REAL check(BonusAmount > 0),
BonusDate DATE,
Reason TEXT NOT NULL
);
```

**Output:**

<img width="1340" height="210" alt="image" src="https://github.com/user-attachments/assets/2b95781b-893f-4b6e-b2ef-432244c6156d" />


**Question 5**
---
Insert a record with EmployeeID 001, Name Sarah Parker, Position Manager, Department HR, and Salary 60000 into the Employee table.

```sql
INSERT INTO Employee VALUES(001,"Sarah Parker","Manager","HR",60000);
```

**Output:**

<img width="1301" height="238" alt="image" src="https://github.com/user-attachments/assets/d7887be2-fa43-4969-9397-3da993191670" />


**Question 6**
---
Create a table named Attendance with the following constraints:
AttendanceID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
AttendanceDate as DATE.
Status as TEXT should be one of 'Present', 'Absent', 'Leave'.

```sql
CREATE TABLE Attendance(
AttendanceID INTEGER PRIMARY KEY,
EmployeeID INTEGER REFERENCES Employees(EmployeeID),
AttendanceDate DATE,
Status TEXT check(Status IN("Present","Absent","Leave"))
);
```

**Output:**

<img width="1249" height="230" alt="image" src="https://github.com/user-attachments/assets/a6db8d90-d8b0-479f-abb1-7bfd62a164c1" />


**Question 7**
---
In the Products table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a third record where some fields are filled, and others are left as NULL.

```sql
INSERT INTO Products(ProductID,Name,Category) VALUES(106,"Fitness Tracker","Wearables");
INSERT INTO Products(ProductID,Name,Category,Price,Stock) VALUES(107,"Laptop","Electronics",999.99,50);
INSERT INTO Products(ProductID,Name,Category,Stock) VALUES(108,"Wireless Earbud","Accessorie",100);
```

**Output:**

<img width="1232" height="198" alt="image" src="https://github.com/user-attachments/assets/a074d952-727e-4aad-8fdd-744727e89a22" />


**Question 8**
---
Write a SQL query to Add a new column mobilenumber as number in the Student_details table.

```sql
ALTER TABLE Student_details ADD COLUMN mobilenumb number;
```

**Output:**

<img width="1327" height="303" alt="image" src="https://github.com/user-attachments/assets/4b80996f-ac86-4397-8b39-10098f32e9b9" />


**Question 9**
---
Insert the below data into the Books table, allowing the Publisher and Year columns to take their default values.

```sql
INSERT INTO Books(ISBN,Title,Author) VALUES
("978-6655443321","Big Data Analytics","Karen Adams");
```

**Output:**

<img width="1188" height="239" alt="image" src="https://github.com/user-attachments/assets/1b2818e4-8202-4b1d-aa99-25380d76440a" />


**Question 10**
---
Create a table named Events with the following columns:

EventID as INTEGER
EventName as TEXT
EventDate as DATE


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
);
```

**Output:**

<img width="1309" height="323" alt="image" src="https://github.com/user-attachments/assets/9f867088-f07f-41ed-a897-d397ae7eb993" />



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
