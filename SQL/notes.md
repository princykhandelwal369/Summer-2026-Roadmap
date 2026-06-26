# Introduction 

A DBMS is a software that stores, organizes and manages data. SQL, on the other hand, is the language that is used to communicate with DBMS. 
The SQL language is universal, however: MySQL, PostgreSQL, SQL Server, Oracle, SQLite are different software products. For instance- if english is a language, then people with different dialects and accents are products of it. MySQL, PostgreSQL, etc. have majorily same syntax except for a few differences.

MySQL, PostgreSQL, SQLite are RDBMS examples, which means it deals with rows and columns, related via keys.

SQL commands are categorised into:
- DDL (Date Definition Language): CREATE, ALTER, DROP
- DML (Date Manipulation Language): INSERT, UPDATE, DELETE
- DQL (Data Query Language): SELECT
- DCL (Date Control Language): GRANT, REVOKE
- TCL (Transaction Control Language): CONTROL ROLLBACK

# Data Types
Different data types are used, which are as follows:
- INT / INTEGER          -- whole numbers
- DECIMAL(p, s)           -- exact decimal, p=total digits, s=digits after decimal
- FLOAT / DOUBLE           -- approximate decimal
- VARCHAR(n)               -- variable-length text, max n chars
- CHAR(n)                  -- fixed-length text
- TEXT                     -- long text, no fixed limit
- DATE                     -- 'YYYY-MM-DD'
- DATETIME / TIMESTAMP    -- date + time
- BOOLEAN                  -- true/false (stored as 0/1 in MySQL)

# Creating database
A database is a container that holds your tables. Before creating tables, you create or select a database to work in.

# Creating table
A table is where actual data lives — structured into rows and columns. When creating it, you define column names, data types, and constraints (rules like "must be unique" or "cannot be empty").

Common constraints: 
- PRIMARY KEY: Uniquely identifies, cannot be NULL, cannot be repeated (For example: Student roll no. is unique and cannot be NULL)
- NOT NULL: Must have a value, can't be left empty
- UNIQUE: Values must be unique and cannot repeat, unlike PRIMARY- it can be NULL
- DEFAULT value: If no value is given during INSERT, the column automatically gets this fallback value.
- AUTO_INCREMENT: The DBMS automatically generates the next number for this column (commonly used with PRIMARY KEY ids), so you don't have to supply it manually.
- FOREIGN KEY: Links the column with the primary key of another table

# Inserting data
INSERT adds new rows in table
(Strings and dates require '')

# Select
It retrieves data from table and is widely used. 

# WHERE
It is used to filter rows and is used with SELECT, UPDATE and DELETE statements. 
- WHERE name LIKE 'A% means name must start with A and %A means name must end with an A
- AND has higher precedence than OR
- Never write '= NULL', always write 'IS NULL'

# ORDER BY
It sorts a column in ascending or descending order. Ascending order is default and is not compulsory to mention, while when doing descednign, desc must be mentioned. 
