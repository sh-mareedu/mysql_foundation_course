  # Introduction to SQL

## What is SQL?

SQL (Structured Query Language) is a powerful language used to interact with relational databases. It enables users to store, retrieve, update, and delete data efficiently. SQL operates through various commands like SELECT (for retrieving data), INSERT (for adding data), UPDATE (for modifying data), and DELETE (for removing data). It supports multiple database management systems such as MySQL, PostgreSQL, SQL Server, and Oracle. SQL is essential for data management in web development, business intelligence, and enterprise applications.

## History of SQL

- SQL was developed in the 1970s at IBM by Donald D. Chamberlin and Raymond F. Boyce. Initially called SEQUEL, it was designed to interact with IBM’s System R, one of the first relational database management systems.

- In 1986, SQL became a standard of the American National Standards Institute (ANSI), followed by ISO standardization in 1987. Over time, it evolved through multiple versions, including SQL-92, SQL:1999, and SQL:2003.

- Today, SQL is widely used in industries like finance, healthcare, and retail for managing relational databases efficiently.

## Importance & Uses

_SQL plays a critical role in managing and interacting with relational databases, making it essential for efficient data handling._

### Importance of SQL:
- Data Management – Allows structured storage, retrieval, and modification of data.
- Efficiency – Optimizes querying and processing large amounts of data.
- Integration – Works with various technologies, enhancing application functionality.

### Uses of SQL:
- Database Administration – Helps in creating, updating, and maintaining databases.
- Data Analysis – Retrieves specific information for decision-making and business insights.
- Reporting – Generates reports for financial, healthcare, and business analytics.

## Types of SQL commands

_SQL commands are divided into five major categories, each serving a specific role in database management_

**1. Data Definition Language (DDL) – Defines and modifies database structures.**

- CREATE – Creates new databases, tables, or indexes.
- ALTER – Modifies existing tables (e.g., adding columns).
- DROP – Deletes tables or databases permanently.
- TRUNCATE – Removes all records from a table but keeps its structure intact.

**2. Data Manipulation Language (DML) – Handles data within tables.**

- INSERT – Adds new records to a table.
- UPDATE – Modifies existing records.
- DELETE – Removes records from a table.

**3. Data Query Language (DQL) – Retrieves data from databases.**

- SELECT – Fetches specific records using conditions.

**4. Data Control Language (DCL) – Manages user access permissions.**

- GRANT – Assigns specific privileges to users.
- REVOKE – Removes privileges from users.

**5. Transaction Control Language (TCL) – Handles transactions to maintain consistency.**

- COMMIT – Saves all changes permanently.
- ROLLBACK – Reverts changes if an error occurs.
- SAVEPOINT – Sets a checkpoint to rollback partial transactions.

**The combination of these commands ensures seamless database management, allowing users to maintain accuracy, efficiency, and security while handling structured data.**

## SQL Basics

_Database Terminology- Here are some key terms related to databases:_

- Database – A structured collection of data stored electronically.
- Table – A set of rows and columns that holds related data.
- Record (Row) – A single entry in a table.
- Column (Field) – Represents a specific attribute in a table.
- Primary Key – A unique identifier for each record in a table.
- Foreign Key – A field in one table that links to the primary key of another table.
- Index – A performance optimization technique for faster data retrieval.
- SQL Query – A command written in SQL to interact with a database.

## SQL Syntax Rules

_SQL follows a structured syntax to interact with databases efficiently. Here are some Fundamental rules:_

- SQL Statements End with a Semicolon (;) – This marks the end of a statement.
```
SELECT * FROM employees;
```
- Keywords are Case-Insensitive – SQL commands can be written in uppercase or lowercase, but uppercase is preferred.
- String Values are Enclosed in Single Quotes (') – Used for text-based data.
```
SELECT * FROM users WHERE name = 'John';
```
- Table and Column Names Should be Meaningful – It’s best practice to use descriptive names for easy understanding.
- Use Proper Indentation and Formatting – Improves readability in complex queries.
```
SELECT id, name, age  
FROM students  
WHERE age > 18  
ORDER BY name;
```
- SQL is Structured with Clauses – Statements can include clauses like WHERE, ORDER BY, GROUP BY.
- Avoid Using SELECT * in Production Queries – Instead, specify needed columns for performance optimization.

**The Following basic SQL rules improves clarity (making queries readable), efficiency (ensuring fast execution), and accuracy (retrieving correct data). By formatting queries well, optimizing performance, and maintaining data integrity, SQL remains a powerful tool for handling databases.**

## Data Types in SQL

_SQL provides different data types to define the kind of values stored in database tables. They ensure data integrity and optimize storage._

### 1. Numeric Data Types: Used for storing number

- INT – Whole numbers (e.g., 1, 100, -50).
- FLOAT / DOUBLE – Decimal numbers with precision (e.g., 10.5, 3.14).
- DECIMAL / NUMERIC – Fixed-precision numbers, useful for financial calculations.

### 2. String Data Types: Used for text-based values

- CHAR(n) – Fixed-length text (e.g., CHAR(10) stores exactly 10 characters).
- VARCHAR(n) – Variable-length text, saves space by storing only required characters.
- TEXT – Stores long text data.

### 3. Date & Time Data Types: Used for storing timestamps

- DATE – Stores date values (YYYY-MM-DD).
- TIME – Stores time values (HH:MM:SS).
- DATETIME – Combines date and time (YYYY-MM-DD HH:MM:SS).

### 4. Boolean Data Type

- BOOLEAN – Stores TRUE or FALSE values.

### 5. Binary Data Types: Used for storing images or files

- BLOB – Binary Large Object for storing media files.

**These Data types optimize storage and processing by ensuring structured, efficient, and accurate data management in databases.**

## Relational Database

A relational database consists of multiple tables defined using the CREATE TABLE statement, where each table has columns (attributes) and rows (records) to store structured data. Primary keys uniquely identify records within a table, while foreign keys establish relationships between tables to ensure data integrity. SQL provides various commands like SELECT, INSERT, UPDATE, and DELETE to manage and query relational databases efficiently

## SQL Environment Setup (Brief & Clear Info)

### Setting up an SQL environment requires three key steps:

- Installing RDBMS – Choose and install a relational database system like MySQL, PostgreSQL, or SQL Server using official installers.

- SQL Command Line vs GUI Tools – SQL can be used via the command line (mysql, psql) for direct execution or GUI tools like MySQL Workbench and pgAdmin for an interactive experience.

- Connecting to a Database – Use SQL commands (CONNECT TO database_name) or enter login details (host, username, password) in GUI tools to access the database for queries.

## NoSQL vs SQL: Key Differences

- SQL (Structured Query Language) databases are relational, structured with tables, and use predefined schemas.

- NoSQL (Not Only SQL) databases are non-relational, flexible, and store data in various formats like documents, key-value pairs, graphs, or wide-column stores.

- SQL ensures strong consistency with ACID compliance, while NoSQL offers scalability and high availability, often following BASE principles.

### Hybrid Approaches:

- Many applications combine SQL and NoSQL based on requirements.

- Example: A business might use SQL for transaction processing and NoSQL for analytics or caching, ensuring flexibility and efficiency.

- Some databases, like PostgreSQL and Cosmos DB, support both relational and non-relational models to provide a hybrid approach.

## Use Cases

- SQL Databases: Best for structured data, financial applications, enterprise systems, and transactional applications requiring strong consistency (e.g., MySQL, PostgreSQL, SQL Server).

- NoSQL Databases: Ideal for large-scale, dynamic, and unstructured data like social media, IoT, real-time analytics, and content management (e.g., MongoDB, Cassandra, Firebase).

**Both technologies serve unique purposes, and choosing between them depends on scalability, structure, and application needs.**

In conclusion, SQL is an essential tool for managing structured data efficiently across various applications. It provides powerful commands, functions, constraints, and integration capabilities, allowing seamless interaction with relational databases. By understanding SQL commands and concepts like transactions, joins, and subqueries, users can manipulate and retrieve data effectively. Additionally, NoSQL offers flexibility for handling unstructured data, and hybrid approaches combine both technologies for optimal solutions.

**To solidify your understanding, proceed to the SQL example problems in the next file and apply these concepts practically.**
