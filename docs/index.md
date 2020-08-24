## Welcome to GitHub Pages

You can use the [editor on GitHub](https://github.com/AbbyBounty/DBT-all-daily-Assignment-/edit/master/docs/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
 
 # Day 2

   ```C
    PRN:200243020003
```
 ## Select Statment
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

```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/AbbyBounty/DBT-all-daily-Assignment-/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
