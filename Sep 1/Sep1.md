# DAY 9

```C
PRN : 200243020003
```
## Set operators
#### 1. The HR department needs a list of department IDs for departments that do not contain the job ID ST_CLERK. Use the set operators to create this report.
```sql
SELECT
	department_id
FROM
	departments MINUS
	SELECT
		department_id
	FROM
		employees
	WHERE
		job_id = 'ST_CLERK';
```

#### 2. The HR department needs a list of countries that have no departments located in them. Display the country ID and the name of the countries.
```sql
SELECT
	country_id,
	country_name
FROM
	countries MINUS
	SELECT
		l.country_id,
		c.country_name
	FROM
		locations l
		JOIN countries c ON (l.country_id = c.country_id)
		JOIN departments d ON d.location_id = l.location_id;
```

#### 3. Produce a list of jobs for departments 10, 50, and 20. Display the job ID and department ID by using the set operators.
```sql
SELECT DISTINCT
	job_id,
	department_id
FROM
	employees
WHERE
	department_id = 10
UNION ALL SELECT DISTINCT
	job_id,
	department_id
FROM
	employees
WHERE
	department_id = 50
UNION ALL SELECT DISTINCT
	job_id,
	department_id
FROM
	employees
WHERE
	department_id = 20;
```

#### 4. Create a report that lists the employee IDs and job IDs of those employees who currently have a job title that is the same as their job title when they were initially hired by the company (that is, they changed jobs but have now gone back to doing their original job).
```sql
SELECT
	employee_id,
	job_id
FROM
	employees
INTERSECT
SELECT
	employee_id,
	job_id
FROM
	job_history;
```

#### 5. The HR department needs a report with the following specifications:
- Last name and department ID of all employees from the EMPLOYEES table, regardless of whether or not they belong to a department 
- Department ID and department name of all departments from the DEPARTMENTS table, regardless of whether or not they have employees working in them Write a single query to accomplish this.
```sql
SELECT
	last_name,
	department_id,
	TO_CHAR(NULL)
FROM
	employees
UNION
SELECT
	TO_CHAR(NULL),
	department_id,
	department_name
FROM
	departments;
```    