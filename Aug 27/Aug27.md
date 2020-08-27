# DAY 5

```C
PRN : 200243020003
```

## Converstion Functions

#### 1. Try executing round() and truc() for dates of your choice instead of sysdate
```sql
SELECT
	round(to_date('23-OCT-2020'), 'year')
FROM
	DUAL;

SELECT
	trunc(to_date('23-OCT-2020'), 'year')
FROM
	DUAL;
```
#### 2. Display emp_id,last_name,salary in following format eg: 100 King $24,000 (having $ and comma)
```sql
SELECT
	concat(concat(concat(EMPLOYEE_ID, ' '), LAST_NAME), to_char(salary, '$99,999')) "Employee"
FROM
	EMPLOYEES;
```

#### 3. Display hire_date of employees in following format eg: 17th of January in 1997
```sql
SELECT
	to_char(hire_date, 'fmDDth MON "in"YYYY') "Date"
FROM
	EMPLOYEES;
```

#### 4. Calculate annual salary (12*salary*commission) for employees wheather he earns commission or not.
```sql
SELECT
	first_name,
	nvl2 (round(12 * salary * COMMISSION_PCT),
		'earn',
		'do Not earn') commison
FROM
	EMPLOYEES;
```

#### 5. Write a query to display empid ,annual salary for all employees also next column should describe 'sal+comm' or 'sal' accordingly. Eg: 179 sal+comm 7440
```sql
SELECT
	first_name,
	salary + NVL (COMMISSION_PCT,
		0) "SAL+COMM"
FROM
	EMPLOYEES;
```



#### 6. Write a query where organization wants to give a salary increment of $2,000 for all employees.And who get commission, the query should compute the incremented salary added to the commission amount.
```sql 
SELECT
	first_name,
	salary + NVL (COMMISSION_PCT,
		0) "SAL+COMM",
	salary + NVL (COMMISSION_PCT,
		0) + 2000 "increment of 2,000"
FROM
	EMPLOYEES;
```

#### 7. Create a report that produces the following for each employee: <employee last name> earns <salary> monthly but wants <3 times of current salary.>. Label the column Dream Salaries.
```sql
SELECT
	last_name,
	round(salary / 12) "Monthly SALARY",
	salary * 3 "DREAM SALRAY"
FROM
	EMPLOYEES;
```
#### 8. Display each employee?s last name, hire date, and salary review date, which is the first Monday after six months of service. Label the column REVIEW. Format the dates to appear in the format similar to ?Monday, the Thirty-First of July, 2000.?
```sql 
SELECT
	to_date(next_day (add_months (hire_date, '6'), 'mon'), 'dd mon yy') "REVIEW"
FROM
	EMPLOYEES;
```

#### 9. Display the last name, hire date, and day of the week on which the employee started. Label the column DAY. Order the results by the day of the week, starting with Monday.
```sql
SELECT
	first_name,
	to_char(hire_date, 'day')
	day,
	to_char(hire_date, 'd') - 1 Day_number
FROM
	EMPLOYEES
ORDER BY
	Day_number;
```

#### 10. Create a query that displays the employees? last names and commission amounts. If an employee does not earn commission, show ?No Commission.? Label the column COMM.
```sql
SELECT
	last_name,
	nvl2 (COMMISSION_PCT,
		'earn',
		'dont earn')
FROM
	EMPLOYEES;
```

#### 11. Using the DECODE function, write a query that displays the grade of all employees based on the value of the column JOB_ID, using the following data:
```sql
SELECT
	last_name,
	job_id,
	salary,
	decode(job_id, 'AD_PRES', 'A', 'IT_PROG', 'C', 'ST_MAN', 'B', 'SA_REP', 'D', 'ST_CLERK', 'E', 0) "REVISED_SALARY"
FROM
	EMPLOYEES;
```