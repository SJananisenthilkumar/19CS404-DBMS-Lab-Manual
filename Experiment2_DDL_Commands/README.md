<img width="1223" height="352" alt="image" src="https://github.com/user-attachments/assets/25bd817c-437b-4b6d-bb68-a20446295e3b" /># Experiment 2: DDL Commands

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
<img width="1188" height="468" alt="image" src="https://github.com/user-attachments/assets/f22d0369-4abc-4d69-9968-62b9055fa88a" />


```sql
INSERT INTO Student_details (RollNo, Name, Gender)
VALUES (205, 'Olivia Green', 'F');

INSERT INTO Student_details (RollNo, Name, Gender, Subject, MARKS)
VALUES (207, 'Liam Smith', 'M', 'Mathematics', 85);

INSERT INTO Student_details (RollNo, Name, Gender, Subject)
VALUES (208, 'Sophia Johnson', 'F', 'Science');
```

**Output:**

<img width="1223" height="350" alt="image" src="https://github.com/user-attachments/assets/ade45b8b-501a-49bd-9695-cf8fd7dfa70a" />


**Question 2**
---
<img width="1223" height="403" alt="image" src="https://github.com/user-attachments/assets/c2159bbf-b143-4adf-92dd-fccd6161959c" />


```sql
CREATE table Products(
ProductID INTEGER primary key,
ProductName TEXT unique not NULL,
Price REAL check(Price>0),
StockQuantity INTEGER check(StockQuantity>=0)
);
```

**Output:**

<img width="1211" height="341" alt="image" src="https://github.com/user-attachments/assets/5c840fd9-01a5-44bc-85b7-8221f818570b" />


**Question 3**
---
<img width="1184" height="580" alt="image" src="https://github.com/user-attachments/assets/f1a537d2-4b6e-42e3-a028-176b28c8ae2e" />


```sql
ALTER table customer ADD column email VARCHAR(100);
```

**Output:**

<img width="1226" height="425" alt="image" src="https://github.com/user-attachments/assets/0a5b5ef2-0457-474b-9638-2b1d2fb454df" />


**Question 4**
---
<img width="1211" height="440" alt="image" src="https://github.com/user-attachments/assets/1dbb43df-27c0-40e0-b7c9-4cca4ff6b27b" />


```sql
CREATE table Employees(
EmployeeID INTEGER primary key,
FirstName TEXT NOT NULL,
LastName TEXT NOT NULL,
Email TEXT unique,
Salary REAL check(Salary>0),
DepartmentID INTEGER,
FOREIGN KEY (DepartmentID) REFERENCES Departments(DepartmentID)
);
```

**Output:**

<img width="1212" height="493" alt="image" src="https://github.com/user-attachments/assets/d70ab934-edd0-4a9a-9b16-c182dbf2ed40" />


**Question 5**
---
<img width="780" height="351" alt="image" src="https://github.com/user-attachments/assets/748c59b1-2f22-465f-bf3d-ecd861ae1025" />


```sql
CREATE table Products(
ProductID INTEGER primary key,
ProductName TEXT NOT NULL,
Price REAL check(Price>0),
Stock INTEGER check(Stock>=0)
);
```

**Output:**

<img width="1215" height="359" alt="image" src="https://github.com/user-attachments/assets/13b43bb6-55a9-4fcc-a6b1-cf2e6821aaf9" />


**Question 6**
---
<img width="1196" height="279" alt="image" src="https://github.com/user-attachments/assets/cab6c71d-2836-4e10-9a00-42d8efe0a863" />


```sql
INSERT into Products(ProductID,Name,Category)
values(104,'Tablet','Electronics');
```

**Output:**

<img width="1215" height="301" alt="image" src="https://github.com/user-attachments/assets/3c02da46-d9a2-4355-9796-f72e135dfcb2" />


**Question 7**
---
<img width="1221" height="357" alt="image" src="https://github.com/user-attachments/assets/e1c42dce-814b-4900-abf5-52a6c85f7ac3" />


```sql
CREATE table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
ORDERID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

<img width="1213" height="316" alt="image" src="https://github.com/user-attachments/assets/633fc9f9-bf56-4305-9932-87b3d408939f" />


**Question 8**
---
<img width="1169" height="353" alt="image" src="https://github.com/user-attachments/assets/a4b59ba6-8b51-4a53-978d-307f75e465a0" />


```sql
ALTER TABLE Student_details
ADD COLUMN email TEXT NOT NULL DEFAULT 'Invalid';
```

**Output:**

<img width="893" height="349" alt="image" src="https://github.com/user-attachments/assets/bbfd4f2e-75df-4b3c-829d-317c50b60dac" />


**Question 9**
---

<img width="893" height="349" alt="image" src="https://github.com/user-attachments/assets/9800cdf4-b91f-4101-9aa6-6c482e6464ef" />

```sql
INSERT into customers(CustomerID, Name, Address, Email)
SELECT  CustomerID, Name, Address, Email
FROM old_customers;
```

**Output:**
<img width="893" height="349" alt="image" src="https://github.com/user-attachments/assets/a76aec52-d6ce-4549-bd25-0863755e182f" />



**Question 10**
---
<img width="1023" height="399" alt="image" src="https://github.com/user-attachments/assets/417e836c-dacc-493a-a71a-20866aaa8ae8" />


```sql
CREATE table Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT);
```

**Output:**
<img width="1215" height="438" alt="image" src="https://github.com/user-attachments/assets/f5681965-cc8b-4579-9f68-cc177be14d94" />




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.
