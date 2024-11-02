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

1. **Create the Database**:
   - Open pgAdmin or `psql` and create a new database named `Employees_db`.
   
   ```sql
   CREATE DATABASE Employees_db;
   ## Connect to the Database

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
