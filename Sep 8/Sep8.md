# DAY 15
```C
PRN : 2
```

## PL/SQL FUNCTION

1.Write a function which returns basic salary of an employee (DA+HRA+ALLOWANCE). Later use the above function to calculate total salary of employees
2.Write a function which returns max salary of user entered department_id. Use this function to display max salary and its department details
3.Create and compile a function called GET_JOB to return a job title.
Create a VARCHAR2 host variable called TITLE, allowing a length of 35 characters. Invoke the function with SA_REP job ID to return the value in the host variable. Print the host variable to view the result.
4.Create a function called GET_ANNUAL_COMP to return the annual salary computed from an employee?s monthly salary and commission passed as parameters.
Develop and store the GET_ANNUAL_COMP function, accepting parameter values for monthly salary and commission. Either or both values passed can be NULL, but the function should still return a non-NULL annual salary. Use the following basic formula to calculate the annual salary:
(salary*12) + (commission_pct*salary*12)
Use the function in a SELECT statement against the EMPLOYEES table for employees in department 30.

## PL/SQL PROCEDURE
1.Create a procedure called ADD_JOB to insert a new job into the JOBS table. Provide the ID and title of the job using two parameters.
2.Create a procedure called UPD_JOB to update the job title. Provide the job ID and a new title using two parameters. Include the necessary exception handling if no update
3.Create a procedure, ADD_EMPLOYEE, to insert a new employee into the EMPLOYEE table. The procedure should call a VALID_DEPTID function to check whether the department ID specified for the new employee exists in the DEPARTMENTS table.
4.Create a procedure called GET_EMPLOYEE to query the EMPLOYEES table, retrieving the salary and job ID for an employee when provided with the employee ID. Execute the procedure using host variables for the two OUT parameters?one for
the salary and the other for the job ID. Display the salary and job ID for employee ID 120.