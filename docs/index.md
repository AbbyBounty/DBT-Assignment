## Welcome to My Assignment.


  [Day2](#Day2)  [Day3](#Day3)

 
 # Day2

   ```C
    PRN:200243020003
  ```

 
 #### 1. Display table structure for table employees and departments.
 ```sql
DESCRIBE employees;
DESCRIBE departments;
```
#### 2. Check all table names available in your schema.
```sql
SELECT * FROM tab;
```
#### 3. Display all employees data
```sql
 SELECT
    *
FROM
    employees;
```
#### 4. Display all data from departments table
```sql
SELECT
    *
FROM
    departments;
```

#### 5. Display employee_id, last_name,annual salary for all employees also display column heading as "Annual Salary"
```sql
SELECT
    employee_id,
    last_name,
    salary annual_salary
FROM
    employees;
```

#### 6. Display unique job code from employees table
```sql
SELECT DISTINCT
    job_id
FROM
    employees;
```

#### 7. Write a query to display commission value for employees who earn it and 'NULL' should be displayed for employees who do not earn,rename column as "comm"
```sql
SET NULL null;
>SELECT
    first_name,
    commission_pct AS comm
FROM
    employees;
```

#### 8. Write a query to display employee's full name seperated by space.
```sql
SELECT
    first_name
    || ' '
    || last_name
FROM
    employees;
```

#### 9. Write a query to display last_name and job_id as follows eg: King is working as manager and name the column as "Employee Details"
```sql
SELECT
    first_name
    || ' workig as a '
    || job_id AS employee_details
FROM
    employees;
```

#### 10. Display only unique departments from employees table
```sql
SELECT DISTINCT
    department_id,
    last_name,
    salary
FROM
    employees;
```
<br>
<br>
<br>
<br>

## Restricting and Sorting Data

#### 1. Display emp_id,name,salary,commission,department_id for department 80 and rename column as Emp#,Employee,Salary,Comm respectively
```sql
SELECT
    employee_id     AS emp#,
    first_name      AS employee,
    salary          AS salary,
    commission_pct  AS comm
FROM
    employees
WHERE
    department_id = 80;
```


#### 2. Display last_name and first_name for employees having last_name as king
```sql
SELECT
    last_name,
    first_name
FROM
    employees
WHERE
    last_name = 'king';
```

#### 3. Display employee details hired on 23-mar-1998
```sql
SELECT
    *
FROM
    employees
WHERE
    hire_date = '23-mar-1998';
```

#### 4. Display name and salary for employees earning more than 15000 of salary
```sql
SELECT
    first_name,
    salary
FROM
    employees
WHERE
    salary > 15000;
```

#### 5. Display details for those emloyees whose salary in between the amount 8,000 to 20,000
```sql
SELECT
    *
FROM
    employees
WHERE
        salary > 8000
    AND salary < 20000;
```

#### 6. Write a query to display emp_id,last_name,manager_id for all those employees working under managers having id as 100,101,102
```sql
SELECT
    employee_id,
    last_name,
    manager_id
FROM
    employees
WHERE
    manager_id = '100'
    OR manager_id = 101
    OR manager_id = 102;
```

### =========================================================================================================================================

# Day 3


```C
PRN:200243020003
```
### Restricting and Sorting data

#### 1. Display last_name for employees starting with capital 'A'
```sql
SELECT
    employee_id,
    last_name
FROM
    employees
WHERE
    last_name LIKE 'A%';
```

#### 2. Displayfirst_name for employees containing letter 'e'
```sql
SELECT
    employee_id,
    last_name
FROM
    employees
WHERE
    first_name LIKE 'e%';
```

#### 3. Display names for emloyees whose name ends with 's'
```sql
SELECT
    employee_id,
    last_name
FROM
    employees
WHERE
    first_name LIKE '%s';
```

#### 4. Display names for employees hired in month of March
```sql
SELECT
    employee_id,
    last_name,
    hire_date
FROM
    employees
WHERE
    hire_date LIKE '%March%';
```


#### 5. Dislay name, salary, job_id for employees having 'REP' in their job_id
```sql
SELECT
    *
FROM
    employees
WHERE
    job_id = 'REP';
```

#### 6. Display names for employees containing 2nd last letter 'a' in last_name
```sql
SELECT
    employee_id,
    last_name
FROM
    employees
WHERE
    last_name LIKE '_a%';
```



#### 8. Display name, salary,commission for those employees who do not earn commission 
```sql
SELECT
    first_name,
    last_name
FROM
    employees
WHERE
    commission_pct = NULL;
```

#### 9. Display name, salary for employees having salary not in range 5000 to 12000
```sql
SELECT
    first_name,
    last_name,
    salary
FROM
    employees
WHERE
    salary NOT IN ( 5000, 12000 );
```


#### 10. Create a report to display last_name,job_id ,hire_date for employees Matos and Taylor in the same query .Sort data in ascending order by hire_date
```sql
SELECT
    last_name,
    job_id,
    hire_date
FROM
    employees
WHERE
    last_name = 'Matos'
ORDER BY
    hire_date;
```

#### 11. Dislplay data for employees working in department 20 or 50 and sort in alphabetical order of name
```sql
SELECT
    first_name,
    department_id
FROM
    employees
WHERE
    ( department_id = 20
      OR department_id = 50 )
ORDER BY
    first_name;
```

#### 12. Display details for employees who earns between 5000 to 17000 and work in department 20 or 50,Sort data in descending order of salary
```sql
SELECT
    first_name,
    department_id,
    salary
FROM
    employees
WHERE
    salary IN ( 5000, 17000 )
    AND department_id = 20
    OR department_id = 50
ORDER BY
    salary DESC;
```

#### 13. Write a query to display emp_id,last_name,salary for employees working under department which users prompt's while executing query
```sql
 UNDEFINE col;
SELECT
    employee_id,
    last_name,
    department_id,
    &&col
FROM
    employees
WHERE
    department_id = &did
ORDER BY
    &col;
```

#### 14. Write a query to display emp_id,last_name,salary for employees earning salary specified by user and sort data on the basis of user specified column.
```sql
SELECT
    employee_id,
    last_name,
    department_id,
    &&col
FROM
    employees
WHERE
    department_id = &did
ORDER BY
    &col;
```

#### 15. Display salary for employees whose salary is not equal to 2500 or 3500 or 7000 .
```sql
SELECT
    first_name,
    salary
FROM
    employees
WHERE
    salary NOT IN ( 2500, 3500, 7500 );
```    

