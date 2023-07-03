# MegaSoftSql

Briefing.
You work for MegaSoft, a custom software development company. The simplified model of work is as follows:

The company has employees. The following information is known about each employee:
date of birth
level of technical development (can be one of Trainee, Junior, Middle, Senior)
salary in dollars per month
clients contact us with a project. Specialists from the company evaluate the project and fill in the following data for this project:
project start date
project completion date
then employees are assigned to the project
Relationships between entities:

One client can order 0, 1, or more projects. A project always has only one customer.
One employee can work on 0, 1, or more projects. At the same time, 0, 1, or more employees can work on one project
Task #1 - design the database
Create an init_db.sql file in which you model the database structure for MegaSoft according to the briefing. It should contain the following tables:

worker - a table for employees. The table must contain the following fields:
ID - employee identifier, integer, surrogate primary key.
NAME - the name of the employee, a string. Restrictions - must not be NULL, the length must be from 2 to 1000 characters inclusive.
BIRTHDAY - date of birth. The year in this date must be greater than 1900
LEVEL - the level of technical development of the employee. There must be a restriction - this field cannot be NULL, the value of the field can be one of - Trainee, Junior, Middle, Senior
SALARY - employee's salary for 1 month. Limitations - an integer, not less than 100 and not more than 100,000
client - a table for clients. The following fields must be present:
ID - client identifier, integer, surrogate primary key.
NAME - employee name, string. Restrictions - must not be NULL, length must be from 2 to 1000 characters inclusive.
project - a table for projects. The following fields must be present:
ID - project identifier, integer, surrogate primary key.
CLIENT_ID - identifier of the client who ordered this project
START_DATE - the start date of the project
FINISH_DATE - the end date of the project
project_worker - a table showing which employees are working on which projects. Table fields:
PROJECT_ID - project identifier. Foreign key for the project(id) table
WORKER_ID - client identifier. Foreign key for the worker(id) table
the primary key for this table is a composite key, a pair (PROJECT_ID, WORKER_ID)
Task #2 - populate the database
Create the file populate_db.sql, in which write the SQL to fill the tables. After executing the SQL, the database should be in the following state:

at least 10 employees have been added, the minimum salary should be less than 1000, the maximum salary should be more than 5 000, all technical levels (Trainee, Junior, Middle, Senior) should be present
at least 5 clients have been added
at least 10 projects have been added. The duration of each project (difference between START_DATE and FINISH_DATE) should be from 1 to 100 months.
employees are assigned to each project. Each project should have from 1 to 5 employees.
Task #3 - find the employee with the highest salary
Create the file find_max_salary_worker.sql. In it, write SQL that will display the employee with the highest salary. If there are several such employees, you need to display all of them.

An example of the resulting table:

NAME SALARY
John Doe 1000
Task #4 - find the client with the largest number of projects
Create the file find_max_projects_client.sql. In it, write SQL that will display the client with the largest number of projects. If there are several such clients, you need to display all of them.

An example of the resulting table:

PROJECT_COUNT NAME
John Doe 3
Mix Max 3
Task #5 - find the project with the longest duration
Create the file find_longest_project.sql. In it, write SQL that will display the project with the longest duration in months. If there are several such projects, you need to display all of them.

An example of the resulting table:

NAME MONTH_COUNT
Project A 27
Project B 27
Task #6 - find the oldest and youngest employee
Create the file find_youngest_eldest_workers.sql. In it, write SQL that will select the youngest and oldest employees and display them in a table format with the following fields:

TYPE - type (can be YOUNGEST or OLDEST)
NAME - employee's name
BIRTHDAY - date of birth of the employee
If there are several youngest/oldest employees, you need to display them all.

An example of the table:

TYPE NAME BIRTHDAY
YOUNGEST John Doe 2000-01-07
YOUNGEST John Doe 2000-01-07
ELDEST Maxim 1980-06-17
Task #7 - print the cost of each project
Create the file print_project_prices.sql. In it, write SQL that prints a list of projects and the cost of each project.

The cost of a project is the sum of the salaries of employees working on that project multiplied by the duration in months of the project.

For example, employees Max (salary 1000) and Joe (salary 1500) are working on Project A. The project lasts 17 months. Then the cost of Project A = 17 * (1000 + 1500) = 42500

Sort the projects in descending order - display the most expensive projects first.

Example of a table:

NAME PRICE
Project A 42500
Project B 18000
Task #8 - organize everything in a Github repository
Create a new repository on GitHub. Add all the created .sql files there. Make sure there are no unnecessary files in the repository.

The result of the task is a GitHub repository with all the SQL files.
