
# DBT Daily Assignment;


### Aug 24
      Select statement
      1. Display table structure for table employees and departments. 2. Check all table names available in your schema.
      3. Display all employees data
      4. Display all data from departments table
      5. Display employee_id, last_name,annual salary for all employees also display column heading as "Annual Salary"
      6. Display unique job code from employees table
      7. Write a query to display commission value for employees who earn it and 'NULL' should be displayed for employees who do not earn,rename column as "comm"
      8. Write a query to display employee's full name seperated by space.
      9. Write a query to display last_name and job_id as follows eg: King is working as manager and name the column as "Employee Details"
      10. Display only unique departments from employees table
      11. Display unique departments and employee_id,last_name,salary working in those departments

      Restricting and Sorting Data
      1. Display emp_id,name,salary,commission,department_id for department 80 and rename column as Emp#,Employee,Salary,Comm respectively
      2. Display last_name and first_name for employees having last_name as king
      3. Display employee details hired on 23-mar-1998
      4. Display name and salary for employees earning more than 15000 of salary

### Aug 25
      1. Display last_name for employees starting with capital 'A'
      2. Displayfirst_name for employees containing letter 'e'
      3. Display names for emloyees whose name ends with 's'
      4. Display names for employees hired in month of March
      5. Dislay name, salary, job_id for employees having 'REP' in their job_id
      6. Display names for employees containing 2nd last letter 'a' in last_name
      7. Display names for employees containing 'a' and 'e' both in the full_name
      8. Display name, salary,commission for those employees who do not earn commission
      9. Display name, salary for employees having salary not in range 5000 to 12000
      10. Create a report to display last_name,job_id ,hire_date for employees Matos and Taylor in the same query .Sort data in ascending order by hire_date
      11. Dislplay data for employees working in department 20 or 50 and sort in alphabetical order of name
      12. Display details for employees who earns between 5000 to 17000 and work in department 20 or 50,Sort data in descending order of salary
      13. Write a query to display emp_id,last_name,salary for employees working under department which users prompt's while executing query 14. Write a query to display emp_id,last_name,salary for employees earning salary specified by user and sort data on the basis of user specified column.
      15. Display salary for employees whose salary is not equal to 2500 or 3500 or 7000
      16. Try out same queries (wherever applicable)with substitution variable.
      

### Aug 27
            1. Try executing round() and truc() for dates of your choice instead of sysdate
            2. Display emp_id,last_name,salary in following format eg: 100 King $24,000 (having $ and comma)
            3. Display hire_date of employees in following format eg: 17th of January in 1997
            4. Calculate annual salary (12*salary*commission) for employees wheather he earns commission or not.
            5. Write a query to display empid ,annual salary for all employees also next column should describe 'sal+comm' or 'sal' accordingly. Eg: 179 sal+comm 7440
            6. Write a query where organization wants to give a salary increment of $2,000 for all employees.And who get commission, the query should compute the incremented salary added to the commission amount.
            7. Create a report that produces the following for each employee: <employee last name> earns <salary> monthly but wants <3 times of current salary.>. Label the column Dream Salaries.
            8. Display each employee?s last name, hire date, and salary review date, which is the first Monday after six months of service. Label the column REVIEW. Format the dates to appear in the format similar to ?Monday, the Thirty-First of July, 2000.?
            9. Display the last name, hire date, and day of the week on which the employee started. Label the column DAY. Order the results by the day of the week, starting with Monday.
            10. Create a query that displays the employees? last names and commission amounts. If an employee does not earn commission, show ?No Commission.? Label the column COMM.
            11. Using the DECODE function, write a query that displays the grade of all employees based on the value of the column JOB_ID, using the following data:

                  job AD_PRES A
            ST_MAN B IT_PROG C

   ### Aug 26
         1. First Rewrite /practice all demo queries taught in session.
      2. Display full names of employees separated by space and initial letter of every word should be in capital, rename column as "Name"
      3. Display last_name in capital letters
      4. Generate login_id for employees consisting upto 5 characters of first_name and initial letter first last_name and underscore as a separator
      5. Display system date through query
      6. Display emp_id,last_name, annual salary rounded to nearest whole number .
      7. Write query to display hike in salary by 15.5% and round to nearest whole number
      8. Modify above query in different script file where you should also display revised salary i.e. old salary subtracted from new salary
      9. Display last_name for employees where starting character will be prompted by user and the case should not affect to output
      10. Display last_name and length of last-name whose names start with 'J' or 'H' or 'T'. Sort data in alphabetical order of names
      11. HR department wants to check for how many months every employee has worked with the organization sort data by order of months. (Hint: calculate months between todays date and hire_date)
      12. Display last_name of employee and indicate the amount of their salaries with asterisks. Each asterisk signifies a thousand dollars sort data in desending order of salary. Eg: king earns 24,000 so 24 asterisks should be displayed and not the salary
      
      
   ### Aug 28
         1. First Rewrite /practice all demo queries taught in session. 2. Display maximum salary from department 20
      3. Display the oldest hire_date from employees
      4. Find out the correct average salary
      5. Display count of employees earning commission
      6. Display department_id,maximum salary department-wise
      7. Display department_id,minimum salary for those departments whose min sal is less than 7000
      8. Write a query to display the number of people with the same job. (count jobwise)
      9. Re-write the above query where user is prompted for job_id. (eg. : "REP" if entered they display all emp with job_id having REP
      10. Find the difference between the highest and lowest salaries. Label the column DIFFERENCE
      11. Create a report to display the manager number and the salary of the lowest-paid employee for that manager. Exclude anyone whose manager is not known. Exclude any groups where the minimum salary is $6,000 or less. Sort the output in descending order of salary.
      12. Create a query to display the total number of employees hired in 1995, 1996, 1997, and 1998. Create appropriate column headings.


### Aug 29
      1. Write a query for the HR department to produce the addresses of all the departments. Use the LOCATIONS and
      COUNTRIES tables. Show the location ID, street address, city, state or province, and country in the output. Use a NATURAL JOIN to produce the results
      2. Write a query to display the last name, department number, and department name for all the employees.
      3. Display the last name, job, department number, and the department name for all employees who work in Toronto (use table LOCATIONS)
      4. Create a report to display employees? last name and employee number along with their manager?s last name and manager number. Label the columns Employee, Emp#, Manager, and Mgr#, respectively
      5. Modify query no. 4 to display all employees including King, who has no manager. Order the results by the employee number.
      6. Create a report for the HR department that displays employee last names, department numbers, and all the employees who work in the same department as a given employee prompted on screen.
      7. Create a query that displays the name, job, department name, salary, and grade for all employees. (use table SALGRADE)
      8. The HR department needs to find the names and hire dates of all the employees who were hired before their managers, along with their managers? names and hire dates.
      9. Display id,city,state for city 'Manchester' (use table states and stations) Describe and check the column headings 10. Display id,city,state and location name for city .(use station and location tables)
      11. Display stateid,statename its city and location
      12. Display custid,name,orderdate,shipping date and total amount of order (use table customer and ord)
      13. Display itemid its actualprice and product description. (use table item and product)
      14. Display all orders with orderdate and total for cuutomer JOCKSPORTS (use table customer and ord)
      