# DAY 11


```C
PRN : 200243020003
```
## Creating and managing tables and adding constraints
#### 1. Create table copy_emp same as employees table
2. Populate the DEPT table with data from the DEPARTMENTS table. Include only columns that you need
3. Create table EMP and add all necessary constraints.Include only the EMPLOYEE_ID, FIRST_NAME, LAST_NAME, SALARY, and DEPARTMENT_ID columns. Name the columns in your new table ID, FIRST_NAME, LAST_NAME, SALARY , and DEPT_ID, respectively.
4. Truncate table EMP
5. Drop the EMP table
6. Now again create table EMP.Add a table-level PRIMARY KEY constraint to the EMP table on the ID column. The constraint should be named at creation. Name the constraint my_emp_id_pk.
7. Create a PRIMARY KEY constraint to the DEPT table using the ID column. The constraint should be named at creation. Name the constraint my_deptid_pk.
8. Modify the EMP table to allow for longer employee last names. Confirm your mod ification.
9. Confirm that both the DEPT and EMP tables are stored in the data dictionary. (Hint: USER_TABLES)
10. Drop the FIRST_NAME column from the EMP table. Confirm your modification by checking the description of the table.
11. Add a column DEPT_ID to the EMP table. Add a foreign key reference on the EMP table that ensures that the employee is not assigned to a nonexistent depar tment. Name the constraint my_emp_dept_id_fk.
12. Confirm that the constraints were added by querying the USER_CONSTRAINTS view. Note the types and names of the constraints.
13. Display the object names and types from the USER_OBJECTS data dictionary view for the EMP and DEPT tables. Notice that the new tables and a new index were created
14. Modify the EMP table. Add a COMMISSION column of NUMBER data type, precision 2, scale 2. Add a constraint to the commission column that ensures that a co mmission value is greater than zero