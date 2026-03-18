# Experiment 4: Aggregate Functions, Group By and Having Clause
### NAME - AANANDHA KANNAN S
### REG NO - 212224040003

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
Write a SQL query that counts the number of unique salespeople. Return number of salespeople.

```sql
SELECT COUNT(DISTINCT salesman_id) as COUNT from orders
```

**Output:**

<img width="390" height="231" alt="image" src="https://github.com/user-attachments/assets/fa0bfb9c-2ecf-4b44-b6f1-ff4c66122680" />


**Question 2**
---
Write a SQL query to find the shortest email address in the customer table?

```sql
SELECT name,email,MIN(LENGTH(email)) as min_email_length
from customer;
```

**Output:**
<img width="960" height="218" alt="image" src="https://github.com/user-attachments/assets/58af8379-c1e8-4bec-824f-875c7dc7b7b8" />


**Question 3**
---
How many appointments are scheduled in each hour of the day?

```sql
select STRFTIME('%H',Appointmentdatetime) as HourOfDay,count(*) as TotalAppointments from appointments group by HourOfDay
order by HourOfDay;
```

**Output:**

<img width="833" height="412" alt="image" src="https://github.com/user-attachments/assets/3138b4c7-8b24-4346-b1b2-137e6f433afd" />


**Question 4**
---
Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.



```sql
select category_id,MIN(price) as Price from products group by category_id  having MIN(price) < 10;
```

**Output:**

<img width="524" height="259" alt="image" src="https://github.com/user-attachments/assets/b8cd099c-2c8b-4999-a57a-fe7801468c58" />


**Question 5**
---
Write the SQL query to find how many patients have more than 3 medical records?.

```sql
select patientID,count(*) as TotalRecords from MedicalRecords group by PatientID having count(*)>3;
```

**Output:**

<img width="617" height="249" alt="image" src="https://github.com/user-attachments/assets/20d8811e-ea7b-4474-8f51-4b08b434f480" />


**Question 6**
---
Write the SQL query that accomplishes the grouping of data by age intervals using the expression (age/5)5, calculates the minimum age for each group, and excludes groups where the minimum age is not less than 25.

```sql
select (age/5)*5 as age_group,MIN(age) from customer1 group by (age/5)*5 having MIN(age)<25;
```

**Output:**

<img width="589" height="226" alt="image" src="https://github.com/user-attachments/assets/6728ca1d-40fa-4243-a4cf-6b9966be692e" />


**Question 7**
---
 Write a SQL query to  find the average salary of all employees?

```sql
select avg(income) as Average_Salary from employee;
```

**Output:**
<img width="462" height="246" alt="image" src="https://github.com/user-attachments/assets/0eeacdb5-5ad9-4343-8fcf-176142779abd" />


**Question 8**
---
Write a SQL query to return the total number of rows in the 'customer' table where the city is not Noida.

```sql
select count(*) as COUNT from customer where city <> 'Noida';
```

**Output:**

<img width="463" height="238" alt="image" src="https://github.com/user-attachments/assets/b8c5c1e3-709a-4f8a-80ab-59ae1afeb499" />


**Question 9**
---
 Write the SQL query that accomplishes the grouping of data by age, calculates the maximum income for each age group, and includes only those age groups where the maximum income is greater than 2,000,000.

```sql
SELECT age,MAX(income) from employee
group by age
having MAX(income)>2000000;
```

**Output:**
<img width="630" height="292" alt="image" src="https://github.com/user-attachments/assets/c979a61e-13bf-473d-9470-be3c3c071e8c" />


**Question 10**
---
Write the SQL query that achieves the grouping of data by age intervals using the expression (age/5)5, calculates the total salary sum for each group, and excludes groups where the total salary sum is not greater than 5000.

```sql
SELECT (age/5)*5 as age_group,SUM(salary) from customer1
group by (age/5)*5
having sum(salary)>5000;
```

**Output:**

<img width="619" height="297" alt="image" src="https://github.com/user-attachments/assets/8e618908-6b28-4208-bfdb-6bada10fa13f" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
