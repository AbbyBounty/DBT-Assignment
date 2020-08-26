
# Day 4

```C
PRN : 200243020003
```
### Single Row Functions

#### 1. First Rewrite /practice all demo queries taught in session.
```sql

SELECT initcap(FIRST_NAME),LOWER(LAST_NAME) FROM EMPLOYEES;
SELECT UPPER('hello'),LOWER('bye') FROM dual;
SELECT first_name,last_name FROM EMPLOYEES WHERE lower(last_name)='king';
SELECT concat('hello ','world')   from dual;
SELECT substr('i love java',1,5) FROM dual;
SELECT instr('i love java','a') FROM dual;
SELECT REPLACE('i love java','l','j') from DUAL;
SELECT rpad(salary,6,'#') FROM EMPLOYEES;
SELECT lpad(salary,6,'#') FROM EMPLOYEES;
SELECT TRIM('j' from 'love java') from dual;
SELECT employee_id, concat(first_name,last_name) name job_id,LENGTH(last_name),instr(last_name,'a') "Contains 'a'?" FROM EMPLOYEES WHERE substr(job_id,4)='REP';
SELECT LENGTH(concat(first_name,last_name)) "length" FROM EMPLOYEES;
SELECT round(67.7) from dual;
SELECT round(67.745,2) from dual;
SELECT trunc(65.358,1) FROM DUAL;
SELECT MOD(25,5)FROM DUAL;
SELECT sysdate FROM DUAL;
SELECT months_between('01-sep-97','01-sep-96') "months" FROM DUAL;
SELECT add_months('01-sep-02',2) "month" FROM DUAL;
SELECT next_day(sysdate,'wed') from DUAL;
SELECT last_day('01-sep-95') FROM DUAL ;
SELECT round(sysdate,'month') FROM DUAL;
SELECT round(sysdate,'year') FROM DUAL;
SELECT hire_date,round(hire_date,'year') FROM EMPLOYEES;
SELECT hire_date,round(hire_date,'month') FROM EMPLOYEES;
SELECT hire_date,round(hire_date,'day') FROM EMPLOYEES;
```
#### 2. Display full names of employees separated by space and initial letter of every word should be in capital, rename column as "Name"
```sql
SELECT
	concat(concat(first_name, ' '), last_name) "Name"
FROM
	EMPLOYEES;
```

#### 3. Display last_name in capital letters
```sql
SELECT
	upper(last_name)
FROM
	EMPLOYEES;
```
#### 4. Generate login_id for employees consisting upto 5 characters of first_name and initial letter first last_name and underscore as a separator
```sql
SELECT
	concat(concat(substr(first_name, 1, 5), '_'), substr(last_name, 1, 1))
FROM
	EMPLOYEES:
```
#### 5. Display system date through query
```sql
SELECT
		sysdate
	FROM
		DUAL;
```

#### 6. Display emp_id,last_name, annual salary rounded to nearest whole number .
```sql
SELECT
	employee_id,
	last_name,
	round(SALARY)
FROM
	EMPLOYEES;
```
#### 7. Write query to display hike in salary by 15.5% and round to nearest whole number
```sql
SELECT
	first_name,
	salary,
	round(mod(salary, 15.5) * 100 + salary) hike
FROM
	EMPLOYEES;
```
#### 8. Modify above query in different script file where you should also display revised salary i.e. old salary subtracted from new salary
```sql
SELECT
	first_name,
	salary,
	round(mod(salary, 15.5) * 100 + salary) hike,
	round(mod(salary, 15.5) * 100) diffrence
FROM
	EMPLOYEES;
```

#### 9. Display last_name for employees where starting character will be prompted by user and the case should not affect to output
```sql
SELECT
	first_name,
	last_name
FROM
	EMPLOYEES
WHERE
	lower(last_name) = 'king';
```

#### 10. Display last_name and length of last-name whose names start with 'J' or 'H' or 'T'. Sort data in alphabetical order of names
```sql
SELECT
	FIRST_NAME,
	LENGTH(last_name)
FROM
	EMPLOYEES
WHERE
	FIRST_NAME LIKE 'J%'
	OR FIRST_NAME LIKE 'H%'
	OR FIRST_NAME LIKE 'T%'
ORDER BY
	FIRST_NAME;
```

#### 11. HR department wants to check for how many months every employee has worked with the organization sort data by order of months. (Hint: calculate months between todays date and hire_date)
```sql
SELECT
	first_name,
	HIRE_DATE,
	round(months_between (sysdate, HIRE_DATE)) "Months worked"
FROM
	EMPLOYEES;
```

#### 12. Display last_name of employee and indicate the amount of their salaries with asterisks. Each asterisk signifies a thousand dollars sort data in desending order of salary. Eg: king earns 24,000 so 24 asterisks should be displayed and not the salary
```sql
SELECT
	last_name,
	concat(rpad(salary, 2, '*'), '****')
FROM
	EMPLOYEES;
```