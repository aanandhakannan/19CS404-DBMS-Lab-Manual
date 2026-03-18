# Experiment 3: DML Commands

### NAME - AANANDHA KANNAN S

### REG NO - 212224040003

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
Write a SQL statement to Update the address to '58 Lakeview, Magnolia' where supplier ID is 5 in the suppliers table.



```sql
-- UPDATE Suppliers
set address='58 Lakeview, Magnolia'
where supplier_id=5;
```

**Output:**

<img width="1038" height="197" alt="image" src="https://github.com/user-attachments/assets/0ae9fd1e-2824-493a-a577-b7128f7a9818" />


**Question 2**
---
Write a SQL statement to show all the contact_name, address, city of all customers who are from 'Germany', 'Mexico' and 'Spain' countries.

```sql
select contactname,address,city from customers where country in ('Germany','Spain','Mexico');
```

**Output:**

<img width="890" height="648" alt="image" src="https://github.com/user-attachments/assets/1deddef4-9aaf-40e0-8f4e-f3be3347eee9" />


**Question 3**
---
Write a SQL query to delete a doctor from Doctors table whose Specialization is 'Pediatrics' and First name is 'Michael'.

```sql
delete from doctors
where first_name is 'Micahel' or  specialization is 'Pediatrics';
```

**Output:**

<img width="1050" height="280" alt="image" src="https://github.com/user-attachments/assets/0f73924d-33de-4d5d-87a1-26199ac122c9" />


**Question 4**
---
Write a SQL query to calculate the discount amount for each product. Return product_id, original_price, discount_percentage, and discount_amount.



```sql
select product_id,original_price,discount_percentage,original_price-(original_price*(1-discount_percentage)) as discount_amount from products; 
```

**Output:**

<img width="1140" height="214" alt="image" src="https://github.com/user-attachments/assets/472d60f7-dab9-4160-8989-719ea31a2db5" />


**Question 5**
---
Write a query to get all the records from EmployeePosition table who have joined in the year 2020.

```sql
select *
from EmployeePosition
where DateofJoining between '2020-01-01' and '2020-12-31';
```

**Output:**

<img width="991" height="224" alt="image" src="https://github.com/user-attachments/assets/704ff1f6-dcf3-4d1e-b048-6a9ab9f027f4" />


**Question 6**
---
Write a SQL statement to Increase the selling price by 15% in the products table where quantity in stock is less than 50 and supplier ID is 10.

```sql
update products
set sell_price=sell_price*1.15
where quantity < 50
and supplier_id=10;
```

**Output:**

<img width="850" height="328" alt="image" src="https://github.com/user-attachments/assets/f81af44f-aae8-4765-8fb0-16e2d090a034" />


**Question 7**
---
Write a query to retrieve the EmpFname and EmpLname in a single column as “FullName”. The first name and the last name must be separated with space from EmployeeInfo table.


```sql
select empFname||' '||emplname as FullName from employeeinfo;
```

**Output:**

<img width="548" height="248" alt="image" src="https://github.com/user-attachments/assets/fa487bc3-2bd7-49e8-a787-a59721b8d1df" />


**Question 8**
---
Write a SQL query to calculate the absolute value of the value1 column from the Calculations table.

```sql
select id,value1, ABS(value1) as absolute_value from calculations;
```

**Output:**

<img width="804" height="219" alt="image" src="https://github.com/user-attachments/assets/0749f886-6e12-44bd-a7b5-dc0942099b4f" />


**Question 9**
---
Write a SQL query to determine the age group of value1 in the Calculations table as 'Child' if it is less than 13, 'Teen' if it is between 13 and 19, and 'Adult' if it is 20 or older.

```sql
select id,value1,
case
when value1 <13 then 'Child'
when value1 between 13 and 19 then'Teen'
else 'Adult'
end as age_group
from calculations;
```

**Output:**

<img width="807" height="283" alt="image" src="https://github.com/user-attachments/assets/9694df8d-6316-4e67-9001-17380ef856eb" />


**Question 10**
---
Write a SQL query to calculate the original price using the discount percentage and the given discounted price. Return product_id, discounted_price, discount_percentage, and original_price
```sql
SELECT product_id,
discounted_price,discount_percentage,discounted_price/(1-discount_percentage) as original_price from products;
```

**Output:**
<img width="1158" height="206" alt="image" src="https://github.com/user-attachments/assets/690b3b8b-f0f9-443a-95b9-d7ecbe4c1fe0" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
