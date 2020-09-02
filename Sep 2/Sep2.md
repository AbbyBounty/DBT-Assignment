# DAY 10

```C
PRN : 200243020003
```
## Manupilating Data

#### 1. Run the statement to build the MY_EMPLOYEE table to be used for the lab.
```sql
CREATE TABLE my_employee (
	id NUMBER (4),
	last_name VARCHAR2 (25),
	first_name VARCHAR2 (25),
	userid VARCHAR2 (8),
	salary NUMBER (9,
		2)
);
```
#### 2. Add the first row of data to the MY_EMPLOYEE table . Do not list the columns in the INSERT clause.Make the data additions permanent.
```sql
INSERT INTO my_employee
		VALUES(1, willl, smith, wsmith, 60000);
COMMIT;
```

#### 3. Populate the MY_EMPLOYEE table with the second row of sample data from the preceding list. This time, list the columns explicitly in the INSERT clause
```sql
INSERT INTO my_employee (id, last_name, first_name, userid, salary)
		VALUES(2, jack, jimmy,jjimmy , 45000);
```
#### 4. Write an INSERT statement in a text file named loademp.sql to load rows into the MY_EMPLOYEE table. Concatenate the first letter of the first name and the f irst seven characters of the last name to produce the user ID.
```sql
SET ECHO OFF SET VERIFY OFF INSERT INTO my_employee
		VALUES(& p_id, & p_last_name, & p_first_name, lower(substr(& p_first_name, 1, 1) || substr(& p_last_name, 1, 7)), & p_salary);
SET VERIFY ON SET ECHO ON;
```

#### 5. Change the last name of employee 3 to Drexler
```sql
UPDATE
	my_employee
SET
	last_name = Drexler
WHERE
	id = 3;
```

#### 6. Change the salary to 1000 for all employees with a salary less t han 900.Verify your changes to the table.
```sql
UPDATE
	my_employee
SET
	salary = 1000
WHERE
	salary < 900;
```
#### 7. Delete an employee from the MY_EMPLOYEE table. Prompt user on screen for first_name
```sql
DELETE FROM MY_EMPLOYEE
WHERE FIRST_NAME = '&name';
```
#### 8. Try all these:: Mark an intermediate point in the processing of the transaction. Empty the entire table.Confirm that the table is empty.
```sql
SAVEPOINT step_8;

DELETE FROM my_employee;

SELECT
	*
FROM
	my_employee;
```

#### 9. Discard the most recent DELETE operation without discarding the earlier INSERT operation.Confirm that the new row is still intact
```sql
ROLLBACK TO step_8;

SELECT
	*
FROM
	my_employee;
```    