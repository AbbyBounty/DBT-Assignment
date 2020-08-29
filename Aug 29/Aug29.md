
# DAY 7

```C
PRN : 200243020003
```
### Displaying data from multiple tables.

 #### 1. Write a query for the HR department to produce the addresses of all the departments. Use the LOCATIONS and COUNTRIES tables. Show the location ID, street address, city, state or province, and country in the output. Use a NATURAL JOIN to produce the results
 ```sql
 SELECT
	d.department_id,
	d.DEPARTMENT_NAME,
	l.location_id,
	l.street_address,
	l.city,
	l.STATE_PROVINCE,
	c.COUNTRY_NAME
FROM
	departments d
	JOIN locations l ON (l.location_id = d.location_id)
	JOIN countries c ON (c.country_id = l.country_id);
```

#### 2. Write a query to display the last name, department number, and department name for all the employees.
```sql
SELECT
	last_name,
	department_id,
	department_name
FROM
	employees
	JOIN departments USING (department_id);
```

#### 3. Display the last name, job, department number, and the department name for all employees who work in Toronto (use table LOCATIONS)
```sql
SELECT
	e.last_name,
	jj.job_title,
	d.department_id,
	d.department_name
FROM
	employees e
	JOIN departments d ON (d.department_id = e.department_id)
	JOIN job_history j ON (j.employee_id = e.employee_id)
	JOIN jobs jj ON (jj.job_id = j.job_id)
	JOIN locations l ON (l.location_id = d.location_id)
WHERE
	city = 'Toronto';
```

#### 4. Create a report to display employees? last name and employee number along with their manager?s last name and manager number. Label the columns Employee, Emp#, Manager, and Mgr#, respectively
```sql
select emp.employee_id "Emp#",emp.last_name "Empname",mgr.employee_id "Mid#",mgr.last_name "Mgrname" from employees emp join employees mgr
on(emp.manager_id=mgr.employee_id);
```
#### 5. Modify query no. 4 to display all employees including King, who has no manager. Order the results by the employee number.
```sql
SELECT
	e.last_name,
	e.employee_id,
	m.last_name,
	m.employee_id
FROM
	employees e
	LEFT JOIN employees m ON (e.manager_id = m.employee_id)
ORDER BY
	e.last_name;
```

#### 6. Create a report for the HR department that displays employee last names, department numbers, and all the employees who work in the same department as a given employee prompted on screen.
```sql
SELECT
	last_name,
	department_id
FROM
	employees
	JOIN departments d USING (department_id)
WHERE
	d.department_name LIKE '%&nm%';
```


#### 7. Create a query that displays the name, job, department name, salary, and grade for all employees. (use table SALGRADE)
```sql
SELECT
	last_name, job_id, department_name, salary, grade
FROM
	employees e
	JOIN departments d USING (department_id)
	JOIN salgrade s ON (e.salary BETWEEN s.losal
	AND s.hisal);
```

#### 8. The HR department needs to find the names and hire dates of all the employees who were hired before their managers, along with their managers? names and hire dates.
```sql
SELECT
	e.last_name,
	e.hire_date,
	m.last_name,
	m.hire_date
FROM
	employees e
	JOIN employees m ON (e.manager_id = m.employee_id)
WHERE
	e.hire_date < m.hire_date;
```


#### 9. Display id,city,state for city 'Manchester' (use table states and stations) Describe and check the column headings 
```sql
SELECT
	id,
	city,
	statename
FROM
	station
	JOIN states ON (stateid = state)
WHERE
	city = 'manchester';
```

#### 10. Display id,city,state and location name for city .(use station and location tables)
```sql
SELECT
	id,
	city,
	state,
	locationname
FROM
	station
	JOIN LOCATION ON (id = locationid);
```

#### 11. Display stateid,statename its city and location
```sql
SELECT
	stateid,
	statename,
	CITY,
	LAT_N,
	LONG_W
FROM
	STATES
	JOIN STATION ON (state = stateid);
```

#### 12. Display custid,name,orderdate,shipping date and total amount of order (use table customer and ord)
```sql
SELECT
	c.custid,
	c.name,
	o.ORDERDATE,
	o.shipdate,
	o.total
FROM
	customer c
	JOIN ord o ON (c.custid = o.custid);
```

### 13. Display itemid its actualprice and product description. (use table item and product)
```sql
SELECT
	itemid,
	actualprice,
	descrip
FROM
	item i
	JOIN product p ON (p.prodid = i.prodid);
```

#### 14. Display all orders with orderdate and total for cuutomer JOCKSPORTS (use table customer and ord)
```sql
SELECT
	o.orderdate,
	o.total
FROM
	customer c
	JOIN ord o ON (o.custid = c.custid)
WHERE
	name = 'JOCKSPORTS';
```