# Experiment 6: Joins

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
<img width="1251" height="405" alt="image" src="https://github.com/user-attachments/assets/ecb86042-5828-483b-8aa4-604f83be79fe" />


```sql
select c.cust_name,s.name from customer c
left join salesman s
on c.salesman_id = s.salesman_id
where c.city = s.city;

```

**Output:**

<img width="765" height="610" alt="image" src="https://github.com/user-attachments/assets/1a180f46-576a-4a1d-910e-772438384fa7" />


**Question 2**
---
<img width="1063" height="755" alt="image" src="https://github.com/user-attachments/assets/b0e911e9-1e02-491f-87e9-83954e8869f4" />


```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    c.cust_name,
    c.city AS customer_city,
    c.grade,
    s.name AS salesman_name,
    s.city AS salesman_city,
    s.commission
FROM orders o
INNER JOIN customer c
    ON o.customer_id = c.customer_id
INNER JOIN salesman s
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1319" height="328" alt="image" src="https://github.com/user-attachments/assets/060aae97-e137-4b2d-9f16-0befb4617ef9" />


**Question 3**
---
<img width="1294" height="725" alt="image" src="https://github.com/user-attachments/assets/c57b0ccd-8a24-4d89-8991-1c47c9874818" />


```sql
SELECT
    C.cust_name AS "Customer Name",
    C.city AS "city",
    S.name AS "Salesman",
    S.city AS "city",
    S.commission
FROM
    customer C
JOIN
    salesman S ON C.salesman_id = S.salesman_id
WHERE
    C.city <> S.city  
    AND S.commission > 0.12; 

```

**Output:**

<img width="1265" height="545" alt="image" src="https://github.com/user-attachments/assets/6f667fa6-a9fe-4235-b905-629d015fd74e" />


**Question 4**
---
<img width="1300" height="543" alt="image" src="https://github.com/user-attachments/assets/ea214ea9-a798-4719-a016-09ddeb4e69f9" />


```sql
SELECT 
  p.*
FROM patients p
INNER JOIN test_results t
  ON p.patient_id = t.patient_id
WHERE t.test_name IN ('Blood Test', 'Blood Pressure')
  AND t.result NOT LIKE '%Normal%';

```

**Output:**

<img width="1317" height="384" alt="image" src="https://github.com/user-attachments/assets/9c6b89d7-df65-4b59-82c2-7ca4d50ce877" />


**Question 5**
---
<img width="1290" height="496" alt="image" src="https://github.com/user-attachments/assets/6d0cfd53-f930-4f68-b5e0-2f5a7336ea62" />


```sql
SELECT 
    c.cust_name,
    c.city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;

```

**Output:**

<img width="1260" height="393" alt="image" src="https://github.com/user-attachments/assets/d4463061-fbe0-4c3a-a02b-9dba717d18d1" />


**Question 6**
---
<img width="1085" height="794" alt="image" src="https://github.com/user-attachments/assets/864f9e6c-a6bb-43e4-ad51-7baa723de57d" />


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
INNER JOIN 
    customer c 
    ON o.customer_id = c.customer_id
INNER JOIN 
    salesman s 
    ON o.salesman_id = s.salesman_id;
```

**Output:**

<img width="1312" height="348" alt="image" src="https://github.com/user-attachments/assets/ff790e64-bbe4-4ee0-861d-4a55e2e56160" />


**Question 7**
---
<img width="1267" height="316" alt="image" src="https://github.com/user-attachments/assets/0c55ed0f-a703-4631-b41e-e7cc8aba53f5" />


```sql
SELECT 
  c.cust_name,
  c.city,
  o.ord_no,
  o.ord_date,
  o.purch_amt
FROM customer c
LEFT JOIN orders o
  ON c.customer_id = o.customer_id
WHERE c.city = 'London';

```

**Output:**

<img width="1289" height="422" alt="image" src="https://github.com/user-attachments/assets/f49182cf-ef76-4f2b-b6ae-150f36cf47c0" />


**Question 8**
---
<img width="1206" height="767" alt="image" src="https://github.com/user-attachments/assets/92cacf84-09c2-49d7-9818-90c7ef3366d2" />


```sql
SELECT
    c.cust_name,
    c.city,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s
ON 
    c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;

```

**Output:**

<img width="1268" height="473" alt="image" src="https://github.com/user-attachments/assets/9bcd43f0-7629-4fd4-a2a4-4376b3f4b691" />


**Question 9**
---
<img width="1296" height="656" alt="image" src="https://github.com/user-attachments/assets/a08f68d7-2e3d-42d1-a3ea-092b3101794a" />


```sql
SELECT 
  p.*,
  d.specialization AS doctor_specialization
FROM patients p
INNER JOIN doctors d
  ON p.doctor_id = d.doctor_id;

```

**Output:**

<img width="1324" height="500" alt="image" src="https://github.com/user-attachments/assets/3fac9dbc-dde3-4097-9370-976b1da0b6e0" />


**Question 10**
---
<img width="1298" height="546" alt="image" src="https://github.com/user-attachments/assets/391b1537-c84e-4c42-ab6e-b2a7c1ca58ff" />


```sql
SELECT 
  p.first_name AS patient_name,
  t.result_id,
  t.patient_id,
  t.test_name,
  t.result,
  t.test_date
FROM patients p
INNER JOIN test_results t
  ON p.patient_id = t.patient_id
WHERE p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';

```

**Output:**

<img width="1318" height="381" alt="image" src="https://github.com/user-attachments/assets/e6e5044a-9d7e-4933-bf48-69fda3bda04e" />



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.
