# Experiment 4: Aggregate Functions, Group By and Having Clause

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
<img width="1002" height="560" alt="image" src="https://github.com/user-attachments/assets/f1573113-7bae-4edd-a751-b8356b038c08" />


```sql
select Specialty ,count(Specialty) as TotalDocto from Doctors
group by Specialty;
```

**Output:**

<img width="703" height="741" alt="image" src="https://github.com/user-attachments/assets/e2ff19f8-2bf2-49b2-b063-3b9d3e45a89e" />


**Question 2**
---
<img width="526" height="581" alt="image" src="https://github.com/user-attachments/assets/1bee27cf-d707-4aac-a4da-bbf82ef690d2" />


```sql
select PatientID,count(AppointmentID) as TotalAppointments from Appointments
group by PatientID;
```

**Output:**

<img width="691" height="698" alt="image" src="https://github.com/user-attachments/assets/b8feed06-a929-47c0-9d84-23d3515e93f3" />


**Question 3**
---
<img width="990" height="490" alt="image" src="https://github.com/user-attachments/assets/5dc61571-cdd6-403c-8c44-bb94d30228a8" />


```sql
select PatientID,count(Medications)as AvgMedications from MedicalRecords
group by PatientID;
```

**Output:**

<img width="645" height="667" alt="image" src="https://github.com/user-attachments/assets/98bb9f4f-4ef9-4575-a80c-c3c0c3ee8a54" />


**Question 4**
---
<img width="660" height="496" alt="image" src="https://github.com/user-attachments/assets/790124ca-002c-4869-baf4-66f011419120" />


```sql
select name as Employee_Name,age as Age from employee
group by age limit 1;
```

**Output:**

<img width="613" height="373" alt="image" src="https://github.com/user-attachments/assets/dc1df9ed-4973-4dfd-b3ae-a5e72f32b6e9" />


**Question 5**
---
<img width="672" height="526" alt="image" src="https://github.com/user-attachments/assets/375138a1-17c9-4de1-8d4d-f65f8f35996e" />


```sql
select name as fruit_name,inventory as lowest_quantity from fruits
group by inventory limit 1;
```

**Output:**

<img width="656" height="372" alt="image" src="https://github.com/user-attachments/assets/a87c0b3c-7815-4fbe-9bc3-aa7143ad99d8" />


**Question 6**
---
<img width="1020" height="458" alt="image" src="https://github.com/user-attachments/assets/b4ca8a24-cebe-4c8b-87dc-a123237b24e3" />


```sql
select max(age)-min(age) as age_difference from employee
```

**Output:**

<img width="426" height="382" alt="image" src="https://github.com/user-attachments/assets/6540122a-025c-4e63-a93c-1ca59441ed6f" />


**Question 7**
---
<img width="943" height="485" alt="image" src="https://github.com/user-attachments/assets/264daf7c-dcda-409e-9d2f-fb1be4e08488" />


```sql
select COUNT(*) as COUNT from customer where city <> 'Noida';
```

**Output:**

<img width="423" height="366" alt="image" src="https://github.com/user-attachments/assets/478e17d6-7d37-49b5-a9b0-8ef4321f700f" />


**Question 8**
---
<img width="1200" height="569" alt="image" src="https://github.com/user-attachments/assets/15491089-ad6d-4eff-adad-54f22a3bc353" />


```sql
select city,sum(income) as Income from employee
group by city
having sum(income)>200000;
```

**Output:**

<img width="565" height="594" alt="image" src="https://github.com/user-attachments/assets/d230c18c-5c8a-41b1-b96d-a4e52b72d565" />


**Question 9**
---
<img width="1197" height="477" alt="image" src="https://github.com/user-attachments/assets/28d5c523-46de-40a2-8693-1af9a48784f4" />


```sql
select (age/5)*5 as age_group,SUM(salary) from customer1
group by age_group
having sum(salary)>5000;
```

**Output:**

<img width="591" height="428" alt="image" src="https://github.com/user-attachments/assets/f31e019d-3ed0-46df-bad0-6665c0e030bc" />


**Question 10**
---
<img width="1185" height="455" alt="image" src="https://github.com/user-attachments/assets/a7c70e2c-23b9-40b0-811e-4fa86798897d" />


```sql
select jdate,AVG(workhour) from employee1
group by jdate
having avg(workhour)<10;
```

**Output:**

<img width="629" height="411" alt="image" src="https://github.com/user-attachments/assets/844de514-22eb-41e7-9967-49e152fa8768" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.
