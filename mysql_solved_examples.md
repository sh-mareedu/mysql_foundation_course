# SQL Database Commands

To further enhance your grasp of SQL, the following file provides a range of solved example problems using the MySQL platform.
These examples cover fundamental to advanced SQL commands, offering a structured approach to learning. By working through these problems,
 you will develop a clearer and more practical understanding of SQL concepts, ensuring a strong foundation for real-world applications.

## Data Definition Language (DDL)
_It consists of SQL commands used to define, modify, and manage database structures without manipulating data._

- #### CREATE – Defines a new database object like a table.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50),
    age INT,
    department VARCHAR(50)
);
```
- #### ALTER – Modifies an existing database object like adding or removing columns.
```
ALTER TABLE employees ADD COLUMN salary DECIMAL(10,2); 
```
- #### DROP – Permanently removes a database object like a table.
```
DROP TABLE employees;
```
- #### TRUNCATE – Deletes all records from a table without removing its structure.
```
TRUNCATE TABLE employees;
```
- #### RENAME – Changes the name of a database object like a table.
```
RENAME TABLE employees TO staff;
```

## Data Manipulation Language (DML)
_It consists of SQL commands used to insert, update, and delete data within database tables, ensuring dynamic data handling._

- #### INSERT – Adds new records to a table.
```
INSERT INTO employees (id, name, age, department)
VALUES (1, 'John Doe', 30, 'HR');
```
- #### UPDATE – Modifies existing records in a table.
```
UPDATE employees 
SET age = 31 
WHERE id = 1;
```
- #### DELETE – Removes specific records from a table.
```
DELETE FROM employees 
WHERE id = 1;
```

## Data Query Language (DQL)
_It focuses on retrieving data from databases using the SELECT statement._

- #### SELECT Statement – Fetches data from one or more tables.
```
SELECT name, age FROM employees WHERE department = 'HR';
```
- #### Selecting All/Specific Columns – Retrieves either all columns or only the specified ones.
_**Selects all columns:**_
```
SELECT * FROM employees;
```
_**Selects specific columns:**_
```
SELECT name, age FROM employees;
```

## SQL clauses
_In SQL, clauses are components of a query that help refine and structure data retrieval. They define conditions, sorting, grouping, and limits on results.
Clauses work with SQL commands like SELECT, INSERT, UPDATE, and DELETE to manipulate and filter data efficiently_

- #### WHERE – Filters records based on conditions.
```
SELECT * FROM employees WHERE department = 'HR';
```
- #### ORDER BY – Sorts the result set in ascending or descending order.
```
SELECT name, age FROM employees ORDER BY age DESC;
```
- #### GROUP BY – Groups records based on a specified column.
```
SELECT department, COUNT(*) FROM employees GROUP BY department;
```
- #### HAVING – Filters grouped records using aggregate conditions.
```
SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 5;
```
- #### LIMIT / TOP – Restricts the number of records in the result set.
```
SELECT * FROM employees LIMIT 10;
```

## SQL Operators
_SQL operators help manipulate and filter data efficiently._

- #### Arithmetic Operators – Perform mathematical operations like addition, subtraction, multiplication, and division.
```
SELECT salary + 500 AS updated_salary FROM employees;
```
- #### Comparison Operators – Compare values using =, !=, <, >, <=, >=.
```
SELECT * FROM employees WHERE age >= 30;
```
- #### Logical Operators – Combine multiple conditions using AND, OR, NOT.
```
SELECT * FROM employees WHERE department = 'HR' AND age > 25;
```
- #### BETWEEN – Selects values within a given range.
```
SELECT * FROM employees WHERE age BETWEEN 25 AND 35;
```
- #### IN – Matches values in a predefined list.
```
SELECT * FROM employees WHERE department IN ('HR', 'Finance', 'IT');
```
- #### LIKE – Searches for patterns using % (wildcard).
```
SELECT * FROM employees WHERE name LIKE 'J%'; -- Names starting with 'J'
```
- #### IS NULL – Checks for NULL values.
```
SELECT * FROM employees WHERE salary IS NULL;
```

## SQL functions
_SQL functions are built-in operations that perform calculations, data manipulation, or formatting on database values, returning a single result._

- #### Aggregate Functions – Perform calculations on a set of values and return a single value.
```
SELECT COUNT(*) AS total_employees, AVG(salary) AS avg_salary FROM employees;
```
- #### String Functions – Manipulate string data like concatenation, length, and case conversion.
 _**This query concatenates (joins together) the name and department columns into a single string**_
```
SELECT CONCAT(name, ' - ', department) AS employee_info FROM employees;
```
_**This query converts the name column to uppercase using the UPPER() function**_
```
SELECT UPPER(name) AS uppercase_name FROM employees;
```
- #### Date Functions – Handle date and time values, extracting or formatting them.
```
SELECT NOW() AS current_datetime;
```
- #### Conversion Functions – Convert data types between string, date, and numeric values.
```
SELECT CAST(salary AS DECIMAL(10,2)) FROM employees;
```

## Joins in SQL
_Joins in SQL combine records from multiple tables based on related columns, helping retrieve meaningful connected data._

- #### INNER JOIN – Returns only matching records between tables.
```
SELECT employees.name, departments.department_name 
FROM employees 
INNER JOIN departments ON employees.department_id = departments.id;
```
- #### LEFT JOIN – Returns all records from the left table and matching records from the right table.
```
SELECT employees.name, departments.department_name 
FROM employees 
LEFT JOIN departments ON employees.department_id = departments.id;
```
- #### RIGHT JOIN – Returns all records from the right table and matching records from the left table.
```
SELECT employees.name, departments.department_name 
FROM employees 
RIGHT JOIN departments ON employees.department_id = departments.id;
```
- #### FULL JOIN – Returns all records when there is a match in either table.
```
SELECT employees.name, departments.department_name 
FROM employees 
FULL JOIN departments ON employees.department_id = departments.id;
```
- #### CROSS JOIN – Returns the Cartesian product of both tables (every combination of rows).
```
SELECT employees.name, departments.department_name 
FROM employees 
CROSS JOIN departments;
```
- #### Self Join – Joins a table to itself based on a related column.
```
SELECT e1.name AS employee, e2.name AS manager 
FROM employees e1 
JOIN employees e2 ON e1.manager_id = e2.id;
```
## SQL Set Operations
_SQL Set Operations combine results from multiple queries using UNION, UNION ALL, INTERSECT, and EXCEPT/MINUS, helping merge or filter data efficiently._

- #### UNION – Combines results from two queries, removing duplicates.
```
SELECT name FROM employees  
UNION  
SELECT name FROM managers;
```
- #### UNION ALL – Combines results from two queries, keeping duplicates.
```
SELECT name FROM employees  
UNION ALL  
SELECT name FROM managers;
 ```
- #### INTERSECT – Returns common records from both queries.
```
SELECT name FROM employees  
INTERSECT  
SELECT name FROM managers;
```
- #### EXCEPT / MINUS – Returns records present in the first query but not in the second.
```
SELECT name FROM employees  
EXCEPT  
SELECT name FROM managers;
```

## Subqueries
_SQL subqueries are nested queries within another SQL query, used to retrieve intermediate results for further processing._

- #### Single Row Subquery – Returns one row as the result.
```
SELECT name FROM employees WHERE salary = (SELECT MAX(salary) FROM employees);
```
- #### Multiple Row Subquery – Returns multiple rows as the result.
```
SELECT name FROM employees WHERE department_id IN (SELECT id FROM departments WHERE location = 'New York');
```
- #### Correlated Subquery – Uses outer query data within the subquery.
```
SELECT name, salary FROM employees e1  
WHERE salary > (SELECT AVG(salary) FROM employees e2 WHERE e1.department_id = e2.department_id);
```
- #### Subquery in SELECT – Used to compute values within a SELECT statement.
```
SELECT name, (SELECT department_name FROM departments WHERE id = employees.department_id) AS department  
FROM employees;
```
- #### Subquery in FROM – Acts as a temporary table for further querying.
```
SELECT avg_salary.department, avg_salary.avg_salary  
FROM (SELECT department_id, AVG(salary) AS avg_salary FROM employees GROUP BY department_id) AS avg_salary;
```
- #### Subquery in WHERE – Used to filter records based on another query’s result.
```
SELECT name FROM employees WHERE salary > (SELECT AVG(salary) FROM employees);
```

## SQL Constraints
_SQL constraints enforce rules on table columns to maintain data integrity, ensuring valid and consistent data using constraints like NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY, CHECK, and DEFAULT._

- #### NOT NULL – Ensures a column cannot have NULL values.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    age INT NOT NULL
);
```
- #### UNIQUE – Ensures all values in a column are distinct.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    email VARCHAR(100) UNIQUE
);
```
- #### PRIMARY KEY – Uniquely identifies each record in a table (combines NOT NULL + UNIQUE).
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    name VARCHAR(50)
);
```
- #### FOREIGN KEY – Establishes a relationship between two tables.
```
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);
```
- #### CHECK – Validates data before insertion or update.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    age INT CHECK (age >= 18)
);
```
- #### DEFAULT – Assigns a default value when no value is provided.
```
CREATE TABLE employees (
    id INT PRIMARY KEY,
    status VARCHAR(20) DEFAULT 'Active'
);
```

## Transactions and Concurrency
_Transactions and Concurrency in SQL ensure data consistency and integrity by managing multiple operations safely using ACID properties and isolation levels._

- #### BEGIN, COMMIT, ROLLBACK – Used to manage transactions.
_**Saves changes**_
```
BEGIN TRANSACTION;
UPDATE employees SET salary = salary + 1000 WHERE department = 'HR';
COMMIT;
```
_**Reverts changes if an issue occurs**_
```
BEGIN TRANSACTION;
UPDATE employees SET salary = salary - 500 WHERE department = 'Finance';
ROLLBACK;
```
- #### Savepoints – Allow partial rollback within a transaction.
```
BEGIN TRANSACTION;
UPDATE employees SET salary = salary + 1000 WHERE department = 'HR';
SAVEPOINT sp1;
UPDATE employees SET salary = salary - 500 WHERE department = 'Finance';
ROLLBACK TO sp1; -- Rolls back only the second update
COMMIT;
```
- #### ACID (Atomicity, Consistency, Isolation, Durability) – Ensures reliable transactions.
- Atomicity – Transactions execute fully or not at all.

- Consistency – Ensures data integrity.

- Isolation – Prevents interference from concurrent transactions.

- Durability – Changes persist even after system failures.

- #### Isolation Levels – Define how transactions interact with each other.
```
SET TRANSACTION ISOLATION LEVEL READ COMMITTED;
```
**Isolation levels include READ UNCOMMITTED, READ COMMITTED, REPEATABLE READ, and SERIALIZABLE, affecting data visibility between concurrent transactions.**

## Stored Procedures and Functions
_Stored Procedures and Functions are reusable SQL blocks that encapsulate logic for efficient execution, improving performance and modularity in databases._

- #### Creating a Stored Procedure – A reusable SQL block performing a set of operations.
```
CREATE PROCEDURE GetEmployeeDetails
AS
BEGIN
    SELECT * FROM employees;
END;
```
- #### Creating a Function – A SQL function that returns a specific value.
```
CREATE FUNCTION GetEmployeeCount()
RETURNS INT
AS
BEGIN
    DECLARE @count INT;
    SELECT @count = COUNT(*) FROM employees;
    RETURN @count;
END;
```
- #### IN Parameter (Input to Procedure) – Accepts values for processing.
```
CREATE PROCEDURE GetEmployeesByDept(@dept VARCHAR(50))
AS
BEGIN
    SELECT * FROM employees WHERE department = @dept;
END;
```
- #### OUT Parameter (Returns a Value from Procedure) – Sends values back.
```
CREATE PROCEDURE GetMaxSalary(@maxSalary DECIMAL(10,2) OUTPUT)
AS
BEGIN
    SELECT @maxSalary = MAX(salary) FROM employees;
END;
```

## Triggers in SQL
_Triggers in SQL are automated actions that execute in response to specific events like INSERT, UPDATE, or DELETE, helping maintain data integrity._

- #### BEFORE INSERT – Executes before a new record is inserted.
```
CREATE TRIGGER before_insert_employee  
BEFORE INSERT ON employees  
FOR EACH ROW  
SET NEW.created_at = NOW();
```
- #### AFTER INSERT – Executes after a new record is inserted.
```
CREATE TRIGGER after_insert_employee  
AFTER INSERT ON employees  
FOR EACH ROW  
INSERT INTO audit_log(action, timestamp) VALUES ('New employee added', NOW());
```
- #### BEFORE UPDATE – Executes before a record is updated.
```
CREATE TRIGGER before_update_employee  
BEFORE UPDATE ON employees  
FOR EACH ROW  
SET NEW.updated_at = NOW();
```
- #### AFTER UPDATE – Executes after a record is updated.
```
CREATE TRIGGER after_update_employee  
AFTER UPDATE ON employees  
FOR EACH ROW  
INSERT INTO audit_log(action, timestamp) VALUES ('Employee record updated', NOW());
```
- #### BEFORE DELETE – Executes before a record is deleted.
```
CREATE TRIGGER before_delete_employee  
BEFORE DELETE ON employees  
FOR EACH ROW  
INSERT INTO audit_log(action, timestamp) VALUES ('Employee record deleted', NOW());
```
- #### AFTER DELETE – Executes after a record is deleted.
```
CREATE TRIGGER after_delete_employee  
AFTER DELETE ON employees  
FOR EACH ROW  
INSERT INTO archive_table VALUES (OLD.id, OLD.name, OLD.department);
```

## 📌 Summary

This file provides practical solutions for working with databases, ensuring effective data management. It covers:

- ✅ Creating and modifying database structures.
- ✅ Managing records with insertion, updates, and deletions.
- ✅ Retrieving and filtering data efficiently.
- ✅ Performing calculations, formatting, and conversions.
- ✅ Combining tables to extract meaningful relationships.
- ✅ Using subqueries for advanced filtering.
- ✅ Enforcing data integrity through constraints.

With structured SQL examples, this resource helps users develop a clear and practical understanding of SQL concepts.
