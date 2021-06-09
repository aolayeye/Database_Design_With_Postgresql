# Pewlett-Hackard-Analysis
## Overview
The Pewlett-Hackard-Analysis is about creating database designs or Entity Relationship Diagrams, designing and managing tables and writing SQL queries to explore and manipulate data in database tables. SQL queries will ask questions from our data and discover the relationships between different data tables using relational databases. In the PH Analysis, we would design a database to address two issues the company faces as its baby boomer generation begins to retire. 1) The company is offering retirement packages for those who meet certain criteria, and 2) the comapny wants to know which positions will need to be filled in the near future when many employees retire at the same time. 

To answer these broad questionsour analysis will reframe the ask into two questions:
1. Who will be retiring in the next few years
2. How many positions will Pewlett-Hackard need to fill

This analysis will help future-proof the company by generating a list of all employees eligible for the retirement package.

In the first part of our analysis, we will create a database design or Entity Relationship Diagram from the CSV files the company has been using to manage its employee data for many years. we would apply data modellling, engineering and analysis skills to get the PH database running.

In the second part of our analysis, we will use SQL queries to determine the number of retiring employees per title, and identify employees who are eligible to participate in a mentorship program. In the end, will prepare a report to help the company prepare for the large scale retirement.

### Phase 1: Control Flow
1. Identify and define the common columns in the employee CSVs.
2. Determine entity relationships by identifying primary keys and foreign keys
3. Create an Entity Relationship Diagram by defining table name, columns, data types and specify primary keys and foreign keys
4. Create the employee database
5. Create the database schmema - this will contain all the tables indentified in the ERD
6. Import the csv files into the appropriate tables
7. Write SQL query to determine retirement eligibility
      * Create new table to hold the employee retirement info
      * Write SQL query to determine current employees by joining the retirement info table with the dept emp table; filter by the to_date column to give the list of employees that are with the company
      * By joinning the current emplyee table with the dep employee table write a query to determine the count of employees retiring by department.
      * Write SQL to determine employee info by joining columns from the employees, salaries, and department tables
      * Write SQL to determine manager info by joining columns from the current employees, departments, and department manager tables
      * Write SQL to determine department retirees by adding department to the current employee table.

#### Entity Relationship Diagram

### Phase 2: Control Flow
1. The Number of Retiring Employees by Title
      * Write a query to determine retirement titles
      * Using the DISTICT ON statement, retrieve the first occurrence of the employee number for each set of rows defined by the ON () clause.
      * Select the query result into a new unique_titles table.
      * Write another query to retrieve the number of employees by their most recent job title who are about to retire.

2. The Employees Eligible for the Mentorship Program
      * Retrieve the emp_no, first_name, last_name, and birth_date columns from the Employees table
      * Retrieve the from_date and to_date columns from the Department Employee table.
      * Retrieve the title column from the Titles table.
      * Use a DISTINCT ON statement to retrieve the first occurrence of the employee number for each set of rows defined by the ON () clause.
      * Select the query result into a new mentorship_eligibilty table. 
      * Join the Employees and the Department Employee tables on the primary key and the Employees and the Titles tables on the primary key.
      * Filter the data on the to_date column to all the current employees, then filter the data on the birth_date columns to get all the employees whose birth dates are between January 1, 1965 and December 31, 1965.
      * Order the table by the employee number.

### Results
* With 29414, employees with Senior Engineer title are most eligible for retirement.
* There are only 2 employees with Manager as their title that are eligible for retirement.
* There are 1549 employees eligible for the mentorship program.
* Using the COUNT we determine that the Production and Development departments with 322 and 396 have the highest count of employees eligible for the mentorship program
* Similarly, using COUNT we also dermine that the Senior Staff and Engineer titles with 569 and 501 counts are the most of all eligible titles.
