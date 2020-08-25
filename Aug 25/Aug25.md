# Day 3


```C
    PRN:200243020003
```

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
    hire_date LIKE '%AUG%';
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