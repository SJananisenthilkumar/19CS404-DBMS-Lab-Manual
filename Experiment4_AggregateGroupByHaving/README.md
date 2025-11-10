
'[;PLOKIMJU# Experiment 4: Aggregate Functions, Group By and Having Clause

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
<img width="1080" height="579" alt="image" src="https://github.com/user-attachments/assets/2db55641-827a-4852-8ea6-82c47ecd3bce" />


```sql
select Specialty ,count(Specialty) as TotalDocto from Doctors
group by Specialty;
```

**Output:**

<img width="748" height="745" alt="image" src="https://github.com/user-attachments/assets/5a85306d-c30f-4355-803d-30b5ae540b56" />


**Question 2**
---
<img width="587" height="598" alt="image" src="https://github.com/user-attachments/assets/73ce2bc5-dd8f-4270-a908-8373d1a55e44" />


```sql
select PatientID,count(AppointmentID) as TotalAppointments from Appointments
group by PatientID;
```

**Output:**

<img width="694" height="695" alt="image" src="https://github.com/user-attachments/assets/c40f43d6-a2cd-4d63-8dca-40f22a8cf0aa" />


**Question 3**
---
<img width="984" height="500" alt="image" src="https://github.com/user-attachments/assets/f9c9f986-3ceb-4e3b-88cd-ec4f17454398" />


```sql
select PatientID,count(Medications)as AvgMedications from MedicalRecords
group by PatientID;
```

**Output:**

<img width="641" height="672" alt="image" src="https://github.com/user-attachments/assets/33737294-09b3-476f-9bd1-8b08f78bcb54" />


**Question 4**
---
<img width="670" height="490" alt="image" src="https://github.com/user-attachments/assets/85696248-e444-406c-b80b-3a8efc85eb53" />


```sql
select name as Employee_Name,age as Age from employee
group by age limit 1;
```

**Output:**

<img width="619" height="370" alt="image" src="https://github.com/user-attachments/assets/c16ca65a-b63b-4671-b2d9-69e64cd11276" />


**Question 5**
---
<img width="678" height="528" alt="image" src="https://github.com/user-attachments/assets/72355c9b-8018-4b52-b17d-e88412a0604c" />


```sql
select name as fruit_name,inventory as lowest_quantity from fruits
group by inventory limit 1;
```

**Output:**

<img width="646" height="367" alt="image" src="https://github.com/user-attachments/assets/3de8d8ee-8207-4970-b06d-440aa5ce48ed" />


**Question 6**
---
<img width="1019" height="461" alt="image" src="https://github.com/user-attachments/assets/c2f0ceaf-01cc-4845-bada-490c47132303" />


```sql
select max(age)-min(age) as age_difference from employee
```

**Output:**

<img width="435" height="368" alt="image" src="https://github.com/user-attachments/assets/b6fd438f-5fd2-41cd-9c00-63ffb5b60bea" />


**Question 7**
---
<img width="951" height="484" alt="image" src="https://github.com/user-attachments/assets/6b3ab61d-2fa3-4ffc-b907-ddae8e3d6aee" />


```sql
select COUNT(*) as COUNT from customer where city <> 'Noida';
```

**Output:**

<img width="351" height="377" alt="image" src="https://github.com/user-attachments/assets/d9263d69-f0d2-48a2-b42d-1c682b38a3bf" />


**Question 8**
---
<img width="1200" height="569" alt="image" src="https://github.com/user-attachments/assets/b7e626c2-dd62-48bb-a743-e1f18e7800d0" />


```sql
select city,sum(income) as Income from employee
group by city
having sum(income)>200000;
```

**Output:**

<img width="565" height="594" alt="image" src="https://github.com/user-attachments/assets/8480a939-98e0-4606-a900-4cf08fc3b025" />


**Question 9**
---
<img width="1197" height="477" alt="image" src="https://github.com/user-attachments/assets/45f71446-aab4-4a1e-baaf-e09cf1b8e4f6" />


```sql
select (age/5)*5 as age_group,SUM(salary) from customer1
group by age_group
having sum(salary)>5000;
```

**Output:**

<img width="591" height="428" alt="image" src="https://github.com/user-attachments/assets/425eb761-d9a5-48c4-acb3-12896de6c87f" />


**Question 10**
---
<img width="1185" height="455" alt="image" src="https://github.com/user-attachments/assets/81ef5d15-2a2a-4b75-ae6a-9ae28dcf7182" />


```sql
select jdate,AVG(workhour) from employee1
group by jdate
having avg(workhour)<10;
```

**Output:**

<img width="629" height="411" alt="image" src="https://github.com/user-attachments/assets/38fe2cfc-0fe2-4c96-9d1c-4c99089dcbda" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
