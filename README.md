<h1>Applying Filters SQL Queries</h1>


<h2>Description</h2>

My organization is working to make their system more secure. It is my job to ensure the system is safe, investigate all potential security issues, and update employee computers as needed. The following steps provide examples of how I used SQL with filters to perform security-related tasks.

<b>Scenario</b>

As a security professional at a large organization. Part of the job is to investigate security issues to help keep the system secure. I recently discovered some potential security issues that involve login attempts and employee machines.
My task is to examine the organization’s data in their employees and log_in_attempts tables. I'll need to use SQL filters to retrieve records from different datasets and investigate the potential security issues.<br />

<b>Retrieve after hours failed login attempts</b>

There was a potential security incident that had occurred after business hours (after 18:00). All after-hours login attempts that failed needed to be investigated.
The following code demonstrates how I created a SQL query to filter for failed login attempts that occurred after business hours.

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/a9b5bc23-8e8e-4b97-9996-4e52235d2e4d)

The first part of this screenshot is my query, and the second part is a portion of the output. This query filters for failed login attempts that occurred after 18:00. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an AND operator to filter my results to output only login attempts that occurred after 18:00 and were unsuccessful. The first condition is login_time > '18:00', which filters for the login attempts that occurred after 18:00. The second condition is success = FALSE, which filters for the failed login attempts.

<b>Retrieve login attempts on specific dates</b>

A suspicious event occurred on 2022-05-09. Any login activity that happened on 2022-05-09 or on the day before needs to be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that occurred on specific dates.

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/5de075b5-a495-4e1c-a98d-5a45628f9f4c)

The first part of this screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred on 2022-05-09 or 2022-05-08. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with an OR operator to filter my results to output only login attempts that occurred on either 2022-05-09 or 2022-05-08. The first condition is login_date = '2022-05-09', which filters for logins on 2022-05-09. The second condition is login_date = '2022-05-08', which filters for logins on 2022-05-08.

<b>Retrieve login attempts outside of Mexico</b>

After investigating the organization’s data on login attempts, I believe there is an issue with the login attempts that occurred outside of Mexico. These login attempts should be investigated.
The following code demonstrates how I created a SQL query to filter for login attempts that occurred outside of Mexico. 

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/67ac7196-de57-4b77-8b1c-96d8f3fa50bb)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all login attempts that occurred in countries other than Mexico. First, I started by selecting all data from the log_in_attempts table. Then, I used a WHERE clause with NOT to filter for countries other than Mexico. I used LIKE with MEX% as the pattern to match because the dataset represents Mexico as MEX and MEXICO. The percentage sign (%) represents any number of unspecified characters when used with LIKE. 

<b>Retrieve employees in Marketing</b>

My team wants to update the computers for certain employees in the Marketing department. To do this, I have to get information on which employee machines to update.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Marketing department in the East building.

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/ddfd7061-db88-4c84-8ff8-96471be445d7)

The first part of the screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Marketing department in the East building. First, I started by selecting all data from the employee's table. Then, I used a WHERE clause with AND to filter for employees who work in the Marketing department and in the East building. I used LIKE with East% as the pattern to match because the data in the office column represents the East building with the specific office number. The first condition is the department = 'Marketing' portion, which filters for employees in the Marketing department. The second condition is the office LIKE 'East%' portion, which filters for employees in the East building.

<b>Retrieve employees in Finance or Sales</b>

The machines for employees in the Finance and Sales departments also need to be updated. Since a different security update is needed, I have to get information on employees only from these two departments.
The following code demonstrates how I created a SQL query to filter for employee machines from employees in the Finance or Sales departments.

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/4ff7b3cd-fba7-4f79-9781-30f5da870b32)

The first part of this screenshot is my query, and the second part is a portion of the output. This query returns all employees in the Finance and Sales departments. First, I started by selecting all data from the employee's table. Then, I used a WHERE clause with OR to filter for employees who are in the Finance and Sales departments. I used the OR operator instead of AND because I want all employees who are in either department. The first condition is department = 'Finance', which filters for employees from the Finance department. The second condition is department = 'Sales', which filters for employees from the Sales department.

<b>Retrieve all employees not in IT</b>

My team needs to make one more security update on employees who are not in the Information Technology department. To make the update, I first have to get information on these employees.
The following demonstrates how I created a SQL query to filter for employee machines from employees not in the  Information Technology department.

![image](https://github.com/digital-md/Apply-filters-SQL-queries/assets/156498985/2d85d0d3-3e06-4199-9424-7c66c53c73e4)


The first part of the screenshot is my query, and the second part is a portion of the output. The query returns all employees not in the Information Technology department. First, I started by selecting all data from the employee's table. Then, I used a WHERE clause with NOT to filter for employees not in this department.

<b>Summary</b>

I applied filters to SQL queries to get specific information on login attempts and employee machines. I used two different tables, log_in_attempts and employees. I used the AND, OR, and NOT operators to filter for the specific information needed for each task. I also used LIKE and the percentage sign (%) wildcard to filter for patterns.

```
--!>
