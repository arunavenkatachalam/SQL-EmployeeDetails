# sql challenge

Background :

The goal is to do a research project about the people of the company employed during the 1980s and 1990s. The employee database from that period contains six CSV files.

For this project, I designed the tables to hold the data from the CSV files, imported the CSV files into an SQL database, and then answered the business questions. I have performed data modeling, data engineering, and data analysis, respectively.


Data Modeling and Data Engineering :

1. Verified all the files and understood the relationship between the files. 

2. Create an Entity Relationship Diagram(ERD) of the tables using "QuickDBD".  
	a) First create the departments table with dept_no as primary key with datatype Varchar(4) and dept_name as Varchar.
	b) Create a titles table with title_id as the primary key with datatype Varchar(4) and title as Varchar.
	c) Create employees table with emp_no as primary key with datatype Inter, emp_title_id as foreign key from  title_id in titles table, birth_date as date, first_name as Varchar, last_name as Varchar, sex as Varchar, 	        	    hire_date as date.
	d) Create a dept_emp table with foreign key emp_no from the employee's table and dept_no from the department's table.
	e) Create dept_manager table with foreign key dept_no from departments table and emp_no from employees table.
	f) Create a salaries table with foreign key emp_no from the employee's table and salary as Varchar(6).

3. Exported the file in the following formats PNG image(.png) as ERD_Employee_DB, PostgreSQL(.sql) as Employee_DB_Schema and save it inside the folder sql-challenge. Save the 6 csv files inside the folder data in  sql-challenge.

4. Create a new Database Employee_DB and using the Employee_DB_Schema.sql create the tables and import the departments, titles, employee, dept_emp, dept_manager, and salaries tables in the same order. 

Data Analysis :

1. Created a list with the employee number, last name, first name, sex, and salary of each employee by joining the employees and salaries table with the employee number(emp_no) field.

2. Listed the first name, last name, and hire date for the employees who were hired in 1986 

3. Identified the manager of each department along with their department number, department name, employee number, last name, and first name  by joining the department's table with the department employee table,  and titles table.

4. with join operation list each employee's department number, employee number, last name, first name, and department name.

5. Identified the first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B using the employee's table with the condition
   
6. Listed each employee in the Sales department, including their employee number, last name, and first name 

7. List all the employees in the Sales and Development departments, including their employee number, last name, first name, and department name.

8. Observed the frequency of employees sharing the same last name. 

Observation :

1. In a total of 36,150 employees have been hired in the year 1986.

2. There are 24 employees under the title 'Manager'.

3. 20 Employees have their first name as 'Hercules' and last name starting with 'B'.

4. There are no employees who belong to the department 'Sales' and 'Development'. Employees who belong to one department do not belong to another.

Pre-DataModeling Steps :
	
1. As the birth_date and hire_date fields in the employee's table were not formatted properly, so worked on converting the columns into YYYY-MM-DD which is the default format in SQL. 

2. Sorted the emp_no in the employee's table so that there is no issues uploading the files in the database.
