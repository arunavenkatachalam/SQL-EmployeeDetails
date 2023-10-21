# sql challenge

Background :

It’s been two weeks since you were hired as a new data engineer at Pewlett Hackard (a fictional company). Your first major task is to do a research project about people whom the company employed during the 1980s and 1990s. All that remains of the employee database from that period are six CSV files.

For this project, you’ll design the tables to hold the data from the CSV files, import the CSV files into a SQL database, and then answer questions about the data. That is, you’ll perform data modeling, data engineering, and data analysis, respectively.


Data Modeling and Data Engineering :

1. Verify all the csv files and understand the relationship  between the files. 

2. Create a Entity Relationship Diagram of the tables using "QuickDBD".  
	a) First create the departments table with dept_no as primary key with datatype Varchar(4) and dept_name as Varchar.
	b) Create titles table with title_id as primary key with datatype Varchar(4) and title as Varchar.
	c) Create employees table with emp_no as primary key with datatype Integer, emp_title_id as foreign key from  title_id in titles table, birth_date as date, first_name as Varchar, last_name as Varchar, sex as Varchar, 	        	    hire_date as date.
	d) Create dept_emp table with foreign key emp_no from employees table and dept_no from departments table.
	e) Create dept_manager table with foreign key dept_no from departments table and emp_no from employees table.
	f) Create salaries table with foreign key emp_no from employees table and salary as Varchar(6).

3. Export the file in the following formats PNG image(.png) as ERD_Employee_DB, PostgreSQL(.sql) as Employee_DB_Schema and save it inside the folder sql-challenge. Save the 6 csv files inside the folder data in  sql-challenge.

4. Create a new Database Employee_DB and using the Employee_DB_Schema.sql create the tables and import the departments, titles, employee, dept_emp, dept_manager and salaries tables in the same order. 

Data Analysis :

1. List the employee number, last name, first name, sex, and salary of each employee by joining the employees and salaries table with employees.emp_no = salaries.emp_no

2. List the first name, last name, and hire date for the employees who were hired in 1986 by specifying in the where statement extract(year from hire_date) = 1986

3. List the manager of each department along with their department number, department name, employee number, last name, and first nam  by joining the departments table with dept_emp with dept_emp.dept_no =       	         departments.dept_no, employees table with employees.emp_no = dept_emp.emp_no and titles table with employees.emp_title_id = titles.title_id. Along with the condition where titles.title = 'Manager' and 
group by departments.dept_no, employees.emp_no

4. List the department number for each employee along with that employee’s employee number, last name, first name, and department name with the same join in the previous question.

5. List first name, last name, and sex of each employee whose first name is Hercules and whose last name begins with the letter B using employees table with the condition first_name = 'Hercules' and last_name LIKE 'B%'

6. List each employee in the Sales department, including their employee number, last name, and first name with the same join in the previous question along with the condition departments.dept_name = 'Sales'

7. List each employee in the Sales and Development departments, including their employee number, last name, first name, and department name with the same join in the previous question along with the condition departments.dept_name = 'Sales' and departments.dept_name = 'Development'

8. List the frequency counts, in descending order, of all the employee last names (that is, how many employees share each last name) using employees table by displaying last_name, count(last_name) with group by last_name and order by Last_Name_Count desc.

Key Observations :

1. There are totally 36,150 employees has been hired in the year 1986.

2. There are 24 employees under the title 'Manager'.

3. 20 Employees have their first name as 'Hercules' and last name starting with 'B'.

4. There are no employeees who belong to department 'Sales' and 'Development'. Employees who belong to one department does not belong to other group so as both the condition is not satisfied the query returns empty table.

Pre-DataModeling Steps :
	
1. As the birth_date and hire_date field in employees table was not formatted properly, so worked on converting the columns in to YYYY-MM-DD which is the default  format in SQL. 

2. Sorted the emp_no in employees table so that there is no error while uploading the csv file in the database.