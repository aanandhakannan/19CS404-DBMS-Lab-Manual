# Experiment 6: Joins
### NAME - AANANDHA KANNAN S

### REG NO - 212224040003

## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "salesman_name") and the "cust_name" column from the "customer" table (aliased as "customer_name"), with a left join on the "salesman_id" column.



```sql
select s.name as salesman_name ,c.cust_name as customer_name from salesman s
left join customer c
on s.salesman_id=c.salesman_id;
```

**Output:**

<img width="779" height="733" alt="image" src="https://github.com/user-attachments/assets/8246b724-ce50-46be-91b7-7475e0a3081b" />


**Question 2**
---
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c"), and the "ord_no," "ord_date," and "purch_amt" columns from the "orders" table (aliased as "o"), with a left join on the "customer_id" column.

```sql
select c.cust_name as cust_name,o.ord_no,o.ord_date,o.purch_amt from customer c
left join orders o
on c.customer_id=o.customer_id;
```

**Output:**

<img width="1057" height="324" alt="image" src="https://github.com/user-attachments/assets/76925804-321e-4a0c-94e3-8074abcdb067" />


**Question 3**
---
Write the SQL query that accomplishes the selection of all columns from the "patients" table and the first name of doctors from the "doctors" table, with an inner join on the "doctor_id" column.

```sql
select p.*,d.first_name as doctor_name from patients p
inner join doctors d
on p.doctor_id=d.doctor_id;
```

**Output:**

<img width="937" height="270" alt="image" src="https://github.com/user-attachments/assets/e39af8cf-2048-4fb5-a81a-f248676c5495" />


**Question 4**
---
Write the SQL query that achieves the selection of the date of birth from the "patients" table (aliased as "p") and all columns from the "appointments" table (aliased as "a"), with an inner join on the "patient_id" column and a condition filtering for patients with the first name 'Alice'.

```sql
select p.date_of_birth,a.* from patients p 
inner join appointments a
ON p.patient_id = a.patient_id 
WHERE p.first_name = 'Alice';
```

**Output:**

<img width="1235" height="294" alt="image" src="https://github.com/user-attachments/assets/eb979fd8-e267-4d61-9b13-ff89a2af9d55" />


**Question 5**
---
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name") and the first name from the "doctors" table (aliased as "doctor_name"), with an inner join on the "doctor_id" column and a condition filtering for patients with a null discharge date.

```sql
select p.first_name as patient_name,d.first_name as doctor_name from patients p
inner join doctors d
on p.doctor_id=d.doctor_id 
where p.discharge_date IS NULL;
```

**Output:**

<img width="739" height="361" alt="image" src="https://github.com/user-attachments/assets/20c6287d-1e56-4e84-9cc1-d090ddd42253" />


**Question 6**
---
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "s"), the "cust_name," "city," "grade," and "salesman_id" columns from the "customer" table (aliased as "c"), with a left join on the "salesman_id" column.

```sql
select s.name,c.cust_name,c.city,c.grade,c.salesman_id from salesman s
left join customer c
on c.salesman_id = s.salesman_id;

```

**Output:**

<img width="1275" height="263" alt="image" src="https://github.com/user-attachments/assets/446838cb-190f-43a4-9cd5-0505404d190f" />


**Question 7**
---
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c") and the "commission" column from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column.

```sql
select c.cust_name,s.commission from customer c
left join salesman s
on s.salesman_id = c.salesman_id;
```

**Output:**

<img width="564" height="243" alt="image" src="https://github.com/user-attachments/assets/499362ff-33ee-432a-a6ae-2325f3640046" />


**Question 8**
---
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column and a condition filtering for customers in the city 'New York'.

```sql
select s.name from salesman s
where s.city = 'New York';
```

**Output:**

<img width="406" height="303" alt="image" src="https://github.com/user-attachments/assets/30f8d61f-5c46-4340-8498-4907f1397669" />


**Question 9**
---
Write the SQL query that achieves the selection of the "name" column from the "salesman" table (aliased as "s"), the "cust_name," "city," "grade," and "salesman_id" columns from the "customer" table (aliased as "c"), with a left join on the "salesman_id" column and a condition filtering for customers with a grade less than or equal to 100.

```sql
SELECT s.name,c.cust_name,c.city,c.grade,c.salesman_id from salesman s
left join customer c on c.salesman_id=s.salesman_id
where c.grade<=100;
```

**Output:**

<img width="1011" height="305" alt="image" src="https://github.com/user-attachments/assets/a070d124-0157-4346-8b2c-5687e5a80aaf" />


**Question 10**
---
Write the SQL query that achieves the selection of all columns from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column and a condition filtering for customers with the name 'Fabian Johns'.



```sql
SELECT s.* from salesman s 
left join customer c on c.salesman_id=s.salesman_id
where c.cust_name ='Fabian Johns';
```

**Output:**

<img width="992" height="282" alt="image" src="https://github.com/user-attachments/assets/a7737ae5-21d5-4648-a58c-3ece698e54b9" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
