# EX 2 Data Manipulation Language (DML) Commands and built in functions in SQL
## AIM:
To create a manager database and execute DML queries using SQL.


## DML(Data Manipulation Language)
<div align="justify">
The SQL commands that deal with the manipulation of data present in the database belong to DML or Data Manipulation Language and this includes most of the SQL statements. It is the component of the SQL statement that controls access to data and to the database. Basically, DCL statements are grouped with DML statements.
</div>

## List of DML commands: 
<div align="justify">
INSERT: It is used to insert data into a table.<br>
UPDATE: It is used to update existing data within a table.<br>
DELETE: It is used to delete records from a database table.<br>
</div>

## Create the table as given below:
```sql
create table managr(enumber int(6),ename char(15),salary int(5),commission int(4),annualsalary int(7),designation char(10),deptno int(2),reporting char(10));
```
## insert the following values into the table
```sql
insert into manager values(1110,'vidhya',,2500,500,30000,'clerk',10,'John');
insert into manager values(1111,'varsha',3000,400,36000,'manager',null,'James');
insert into manager values(1112,'swetha',3500,300,42000,'manager',30,NULL);
insert into manager values(1113,'divya',4000,0,48000,'clerk',50,'Bond');
```

### Q1) Update all the records of manager table by increasing 10% of their salary as bonus.

### QUERY:
`UPDATE manager SET salary = salary * 1.10;`

### OUTPUT:
![ex 1 (1)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/82eb334b-1cf5-4e41-a59e-1fd150337e79)


### Q2) Delete the records from manager table where the salary less than 2750.

### QUERY:
DELETE FROM manager WHERE salary < 2750;

### OUTPUT:
![ex 1(2)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/1c77645e-9cfa-4e9e-956d-5644377970a9)


### Q3) Display each name of the employee as “Name” and annual salary as “Annual Salary” (Note: Salary in emp table is the monthly salary)

### QUERY:
SELECT ename AS "Name", (salary * 12) + NVL(commission, 0) AS "Annual Salary" FROM manager;
### OUTPUT:


### Q4)	List the names of Clerks from emp table.

### QUERY:
SELECT ename FROM manager WHERE designation = 'clerk';

### OUTPUT:
![ex 1(4)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/366b5931-0285-45a7-be35-d8be1b34d0ff)


### Q5)	List the names of employee who are not Managers.

### QUERY:
SELECT ename FROM manager WHERE designation != 'manager';

### OUTPUT:
![ex 1(5)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/84711c57-81ed-4d32-beb0-e51d9f891939)


### Q6)	List the names of employees not eligible for commission.

### QUERY:
SELECT ename FROM manager WHERE commission = 0;

### OUTPUT:
![ex 1(6)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/bce13436-d26a-42f7-87ab-b7c796f6cf80)


### Q7)	List employees whose name either start or end with ‘s’.

### QUERY:
SELECT ename FROM manager WHERE ename LIKE 'S%' OR ename LIKE '%S';

### OUTPUT:
![ex 1(7)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/f7a422bb-0798-4e26-b358-06d5f41324ea)







### Q8)	List ename, deptno and sal after sorting emp table in ascending order by deptno and then descending order by sal.

### QUERY:
SELECT ename, deptno, salary FROM manager ORDER BY deptno ASC, salary DESC;

### OUTPUT:
![ex 1(10)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/df15e491-45ce-44b9-971b-f86dd862b970)



### Q11) List the names of employees not belonging to dept no 30,40 & 10

### QUERY:
SELECT ename FROM manager WHERE deptno NOT IN (10, 30, 40);
### OUTPUT:
![ex1(11)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/5a04a961-2e28-4f52-8d7c-89bdd868b29d)



### Q12) Find number of rows in the table EMP

### QUERY:
SELECT COUNT(*) AS "Number of Rows" FROM manager;

### OUTPUT:
![ex1(12)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/f6adc75e-a938-4e4f-86ad-efae9627c3a1)


### Q13) Find maximum, minimum and average salary in EMP table.

### QUERY:
SELECT MAX(salary) AS "Maximum Salary", MIN(salary) AS "Minimum Salary", AVG(salary) AS "Average Salary" FROM manager;

### OUTPUT:



### Q14) List the jobs and number of employees in each job. The result should be in the descending order of the number of employees.

### QUERY:
SELECT designation, COUNT(*) AS "Number of Employees" FROM manager GROUP BY designation ORDER BY COUNT(*) DESC;

### OUTPUT:
![ex1(14)](https://github.com/vidhyasrikachapalayam/EX-2-Data-Manipulation-Language-DML-and-Data-Control-Language-DCL-Commands/assets/119477817/93bcc881-061e-44c7-8449-f0b76af9bc53)
### RESULT:
Thus the dml command was executed successfully.

