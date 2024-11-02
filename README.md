# Employee Database SQL Project

## Project Overview

This project is a SQL-based employee management system. It uses PostgreSQL to manage information about employees, departments, salaries, job titles, and department assignments. The database is populated from CSV files and provides various insights through SQL queries.

The project includes:
- Creation of the database schema.
- Importing data from CSV files.
- Executing SQL queries to retrieve specific information about employees, departments, and management.

## Table of Contents

- [Project Overview](#project-overview)
- [Setup Instructions](#setup-instructions)
- [Database Schema](#database-schema)
- [Data Import Instructions](#data-import-instructions)
- [SQL Queries](#sql-queries)
- [Usage Examples](#usage-examples)

## Setup Instructions

### Requirements

- PostgreSQL (v10 or later)
- pgAdmin (optional but recommended for managing the database through a GUI)

### Setting Up the Database

1. **Create the Database**: Open pgAdmin or `psql` and create a new database named `Employees_db`.

2. Connect to the `Employees_db` database in pgAdmin or the `psql` shell.

## Run the Schema File

Use the provided `table_schema.sql` file to create the tables

## Database Schema

The database contains six main tables:

1. **titles**: Stores job titles.
   - Columns: `title_id`, `title`

2. **departments**: Stores department information.
   - Columns: `dept_no`, `dept_name`

3. **employees**: Stores employee personal information.
   - Columns: `emp_no`, `emp_title_id`, `birth_date`, `first_name`, `last_name`, `sex`, `hire_date`

4. **salaries**: Stores salary information for each employee.
   - Columns: `emp_no`, `salary`

5. **dept_emp**: Links employees to departments.
   - Columns: `emp_no`, `dept_no`

6. **dept_manager**: Links department managers to their departments.
   - Columns: `dept_no`, `emp_no`

## Entity Relationship Diagram (ERD)

The ERD diagram file (`ERD.png`) is included in this project to illustrate the relationships between tables. Foreign key constraints ensure data integrity between related tables.

## Data Import Instructions

To populate the tables with data from the CSV files:

In `psql` or pgAdmin, run the following commands in the specified order to avoid foreign key issues:

\copy titles(title_id, title) FROM 'path/to/titles.csv' DELIMITER ',' CSV HEADER;

\copy departments(dept_no, dept_name) FROM 'path/to/departments.csv' DELIMITER ',' CSV HEADER;

\copy employees(emp_no, emp_title_id, birth_date, first_name, last_name, sex, hire_date) FROM 'path/to/employees.csv' DELIMITER ',' CSV HEADER;

\copy salaries(emp_no, salary) FROM 'path/to/salaries.csv' DELIMITER ',' CSV HEADER;

\copy dept_emp(emp

## SQL Queries

The project includes several SQL queries to retrieve data from the database:

1. **Employee Information**: Retrieve employee number, last name, first name, sex, and salary.

2. **Employees Hired in 1986**: Retrieve first name, last name, and hire date for employees hired in 1986.

3. **Department Managers**: Retrieve each department's manager along with their department number, department name, employee number, last name, and first name.

4. **Departmental Employee List**: Retrieve department number, employee number, last name, first name, and department name for each employee.

5. **Specific Name Search**: Retrieve first name, last name, and sex of each employee whose first name is "Hercules" and last name starts with "B".

6. **Sales Department Employees**: Retrieve employee number, last name, and first name of each employee in the Sales department.

7. **Sales and Development Departments**: Retrieve employee number, last name, first name, and department name of each employee in Sales and Development departments.

8. **Frequency of Last Names**: Count and list last names of employees in descending order by frequency.

## Usage Examples

Run these queries in pgAdmin or `psql` to retrieve information from the database. Examples of the queries are included in the project folder in `queries.sql`.

## License

This project is open-source and free to use.

## Acknowledgments

Special thanks to any resources or teams that contributed to the project setup, such as PostgreSQL and pgAdmin documentation.
