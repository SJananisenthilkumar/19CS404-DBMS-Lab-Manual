# Experiment 5: Subqueries and Views

## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
<img width="1062" height="533" alt="image" src="https://github.com/user-attachments/assets/4d081396-fd48-43c8-b5e1-7818736284b7" />


```sql
SELECT name, city FROM customer
WHERE city IN (
    SELECT city
    FROM customer
    WHERE id IN (3, 7)
);

```

**Output:**

<img width="567" height="522" alt="image" src="https://github.com/user-attachments/assets/7ada0909-ea7b-48e4-9613-e385f29d100e" />


**Question 2**
---
<img width="1199" height="614" alt="image" src="https://github.com/user-attachments/assets/89da8afb-0c3a-4a45-bf52-5958349b3a4b" />


```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM ORDERS
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM ORDERS
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

<img width="1265" height="530" alt="image" src="https://github.com/user-attachments/assets/1586a68e-d28e-443d-9e56-e638e766842d" />


**Question 3**
---
<img width="1219" height="613" alt="image" src="https://github.com/user-attachments/assets/4dd590f6-db9f-4a7a-8eb3-0ed1b2c4bd70" />


```sql
SELECT *
FROM Grades g
WHERE grade = (
    SELECT MAX(grade)
    FROM Grades
    WHERE subject = g.subject
);

```

**Output:**

<img width="1274" height="519" alt="image" src="https://github.com/user-attachments/assets/ee21b68d-2f29-44a1-a234-98a05079a5d0" />


**Question 4**
---
<img width="1004" height="532" alt="image" src="https://github.com/user-attachments/assets/795fea52-1e7e-4e94-8457-4318e5b9ddf9" />


```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (SELECT MAX(id) FROM customer)
);

```

**Output:**

<img width="1260" height="566" alt="image" src="https://github.com/user-attachments/assets/d3dd5cde-53d8-46ce-bed9-f21ee421d83a" />


**Question 5**
---
<img width="856" height="435" alt="image" src="https://github.com/user-attachments/assets/86c0aec3-725d-4e8e-b55f-b8d2d87a2cab" />


```sql
SELECT department_id, department_name
FROM Departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name)) FROM Departments
);

```

**Output:**

<img width="571" height="468" alt="image" src="https://github.com/user-attachments/assets/a2b78e0b-9bf1-4668-8b0a-eef89ae3cc9b" />


**Question 6**
---
<img width="835" height="488" alt="image" src="https://github.com/user-attachments/assets/ae2382ae-3561-47c4-a223-1f479bbea6c2" />


```sql
SELECT medication_id, medication_name, dosage
FROM Medications
WHERE dosage = (
    SELECT MIN(dosage)
    FROM Medications
);

```

**Output:**

<img width="871" height="462" alt="image" src="https://github.com/user-attachments/assets/ddb3b3cd-e124-4cf2-ba10-4bf0639d1a31" />


**Question 7**
---
<img width="984" height="734" alt="image" src="https://github.com/user-attachments/assets/d5f6e5f6-73f8-4a4e-bf9a-73026d02bc34" />


```sql
SELECT * FROM CUSTOMERS
WHERE SALARY > 1500;

```

**Output:**

<img width="1227" height="670" alt="image" src="https://github.com/user-attachments/assets/3efa1202-154f-4683-a020-f8a4b07c0aa7" />


**Question 8**
---
<img width="1003" height="714" alt="image" src="https://github.com/user-attachments/assets/11c13ebc-ca35-4e77-addc-c2c27d7c56b0" />


```sql
SELECT *
FROM customer
WHERE customer_id = (
    (SELECT salesman_id FROM salesman WHERE name = 'Mc Lyon') - 2001
);

```

**Output:**

<img width="1267" height="396" alt="image" src="https://github.com/user-attachments/assets/91e3db17-0c64-4358-bf2a-e490cc1d326f" />


**Question 9**
---
<img width="1064" height="552" alt="image" src="https://github.com/user-attachments/assets/c7ce844c-8fee-44b5-9997-3f3d459540cc" />


```sql
SELECT name FROM customer
WHERE phone IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) = 1
);

```

**Output:**

<img width="462" height="531" alt="image" src="https://github.com/user-attachments/assets/78423945-0820-4fa2-a784-78f4440ae984" />


**Question 10**
---
<img width="1189" height="795" alt="image" src="https://github.com/user-attachments/assets/8977754d-2d24-43bc-95d4-b5862f11501e" />

```sql
SELECT o.ord_no, o.purch_amt, o.ord_date, o.customer_id, o.salesman_id
FROM orders o
JOIN salesman s
ON o.salesman_id = s.salesman_id
WHERE s.city = 'New York';

```

**Output:**

<img width="1271" height="544" alt="image" src="https://github.com/user-attachments/assets/a1280628-03fe-42ff-b179-6c422201dbd7" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.
