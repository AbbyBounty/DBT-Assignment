# DAY 12

```C
PRN : 200243020003
```

### Views
#### 1. Create a view called EMPLOYEES_VU based on the employee numbers, employee names, and department numbers from the EMPLOYEES table. Change the heading for the employee name to EMPLOYEE.Display the contents of the EMPLOYEES_VU view. 
```sql
CREATE VIEW emp_vu (
	EMPLOYEE_ID,
	EMPLOYEE,
	DEPARTMENT_ID) AS
SELECT
	EMPLOYEE_ID,
	FIRST_NAME || ' ' || LAST_NAME,
	DEPARTMENT_ID
FROM
	EMPLOYEES;

SELECT
	*
FROM
	emp_vu;
```
#### 2. Select the view name and text from the USER_VIEWS data dictionary view.
```sql
SELECT
	VIEW_NAME
FROM
	USER_VIEWS;
```
#### 3. Using your EMPLOYEES_VU view, enter a query to display all employee names and department numbers.
```sql
SELECT
	EMPLOYEE,
	DEPARTMENT_ID
FROM
	emp_vu;
```

#### 4. Create a view named DEPT50 that contains the employee numbers, employee last names, and department numbers for all employees in department 50. Label the view columns EMPNO, EMPLOYEE, and DEPTNO. Do not allow an employee to be reassigned to another department through the view
```sql
CREATE VIEW dept50 (
	empno,
	EMPLOYEE,
	DEPARTMENT) AS
SELECT
	EMPLOYEE_ID,
	LAST_NAME,
	DEPARTMENT_ID
FROM
	EMPLOYEES
WHERE
	DEPARTMENT_ID = 50;

SELECT
	*
FROM
	dept50;
```

#### 5. Create a view called SALARY_VU based on the employee last names, department names, salaries, and salary grades for all employees. Use the EMPLOYEES, DEPARTMENTS, and JOB_GRADES tables. Label the columns Employee, Department, Salary, and Grade, respectively.
```sql
CREATE VIEW salary_vu (
	EMPLOYEE,
	DEPARTMENT,
	SALARY) AS
SELECT
	e.LAST_NAME,
	d.DEPARTMENT_NAME,
	e.SALARY
FROM
	EMPLOYEES e
	JOIN DEPARTMENTS d ON e.DEPARTMENT_ID = d.DEPARTMENT_ID;

SELECT
	*
FROM
	salary_vu;
```





