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
<img width="1001" height="484" alt="image" src="https://github.com/user-attachments/assets/a8ffdf8f-72e8-4c1a-a7d1-67af773b6dd9" />


```sql
UPDATE Suppliers
SET address='58 Lakeview, Magnolia'
WHERE supplier_ID = 5;
```

**Output:**

<img width="1216" height="462" alt="image" src="https://github.com/user-attachments/assets/0cb284bf-1267-4b64-a801-75114675fe83" />


**Question 2**
---
<img width="1192" height="621" alt="image" src="https://github.com/user-attachments/assets/15b9d94c-b68c-4161-9908-193c7aaf22da" />


```sql
UPDATE purchases
SET per_unit_price = 25,
    total_price = quantity * 25
WHERE purchase_date = '2022-08-15' AND product_id = 12;

```

**Output:**

<img width="1215" height="589" alt="image" src="https://github.com/user-attachments/assets/a2b160f4-887a-4ad8-94ad-e5373278c8f2" />


**Question 3**
---
<img width="1067" height="645" alt="image" src="https://github.com/user-attachments/assets/d93c9980-f26e-40f9-9a6e-2ff3d4ab8b59" />


```sql
update Employees
set email='Unavailable';
```

**Output:**

<img width="1212" height="518" alt="image" src="https://github.com/user-attachments/assets/5c248891-20dd-4473-8702-4ff6fcf6da60" />


**Question 4**
---
<img width="706" height="89" alt="image" src="https://github.com/user-attachments/assets/ce2ccdb3-c45b-4956-9d36-b5e7cd8f659e" />


```sql
update Customer
set grade=5
where city='Chennai';
```

**Output:**

<img width="1221" height="551" alt="image" src="https://github.com/user-attachments/assets/60a68cc7-7e22-47f3-aed1-1b10f093123c" />


**Question 5**
---
<img width="846" height="453" alt="image" src="https://github.com/user-attachments/assets/2a432351-8712-4d35-aa13-a3e612f6b6f1" />


```sql
update suppliers
set supplier_name=upper(supplier_name)
where contact_person like '%Singh%';
```

**Output:**

<img width="1219" height="425" alt="image" src="https://github.com/user-attachments/assets/a295e384-4b18-4f81-8e49-d23cb6a55299" />


**Question 6**
---
<img width="1219" height="635" alt="image" src="https://github.com/user-attachments/assets/3610393d-a551-4c44-8f42-cfc5111e9490" />


```sql
delete from Customer
where WORKING_AREA='New York';
```

**Output:**

<img width="1270" height="687" alt="image" src="https://github.com/user-attachments/assets/7da6aab2-ffd0-40b1-8f25-66bba18b858a" />


**Question 7**
---
<img width="722" height="486" alt="image" src="https://github.com/user-attachments/assets/baf3bf51-c387-421c-aa8b-06585a7126c7" />


```sql
delete from Surgeries
where surgery_id=3;
```

**Output:**

<img width="1215" height="454" alt="image" src="https://github.com/user-attachments/assets/13e191c8-abdf-4c6d-9fc5-119cc9573917" />


**Question 8**
---
<img width="1219" height="510" alt="image" src="https://github.com/user-attachments/assets/b2d2a87f-86af-4e9c-8494-ed79ebc6db7a" />


```sql
DELETE FROM Customer
WHERE GRADE = 2 
  AND CUST_NAME LIKE 'M%' 
  AND PAYMENT_AMT < 3000;

```

**Output:**

<img width="1222" height="466" alt="image" src="https://github.com/user-attachments/assets/96cbdda5-dd66-4505-957a-5af8c461e596" />


**Question 9**
---
<img width="873" height="388" alt="image" src="https://github.com/user-attachments/assets/b94a409b-5641-4d58-b00c-72e9b14684dc" />


```sql
SELECT 
    strftime('%Y', hiredate) AS Year,
    strftime('%m', hiredate) AS Month,
    strftime('%d', hiredate) AS Day
FROM emp;

```

**Output:**

<img width="787" height="431" alt="image" src="https://github.com/user-attachments/assets/62c90c54-3b5d-4d39-a90d-b6e02c75e6cc" />


**Question 10**
---
<img width="902" height="647" alt="image" src="https://github.com/user-attachments/assets/827c6e08-7934-4196-a0f9-4084eec16adf" />


```sql
SELECT *
FROM emp
WHERE hiredate > '2020-01-01';
```

**Output:**

<img width="1217" height="422" alt="image" src="https://github.com/user-attachments/assets/fb642f52-6a49-4305-aade-92165399ce60" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.
