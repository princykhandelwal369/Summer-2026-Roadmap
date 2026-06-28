# Introduction 

A DBMS is a software that stores, organizes and manages data. SQL, on the other hand, is the language that is used to communicate with DBMS. 
The SQL language is universal, however: MySQL, PostgreSQL, SQL Server, Oracle, SQLite are different software products. For instance- if english is a language, then people with different dialects and accents are products of it. MySQL, PostgreSQL, etc. have majorily same syntax except for a few differences.

MySQL, PostgreSQL, SQLite are RDBMS examples, which means it deals with rows and columns, related via keys.

SQL commands are categorised into:
- DDL (Data Definition Language): CREATE, ALTER, DROP
- DML (Data Manipulation Language): INSERT, UPDATE, DELETE
- DQL (Data Query Language): SELECT
- DCL (Data Control Language): GRANT, REVOKE
- TCL (Transaction Control Language): COMMIT, ROLLBACK, SAVEPOINT

--- 

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

---

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

--- 

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

# UPDATE
This modifies existing rows in table. It will modify every row if not used with WHERE

# DELETE
This is used in deleting rows from table. Without the WHERE clause, the whole table will be deleted. This means all rows are deleted, but not the table structure.

# ALTER TABLE
This changes the structure of a table. It is used in adding, deleting and modifying columns. 

# AGGREGATE FUNCTIONS
These functions take many rows and collapse them into a single summary value. Functions include: 
- Total
- Average
- Count
- MIN and MAX

# GROUP BY
Group By groups rows that share the same value in a column. With the help of this, we can run aggregate functions per group instead of the whole table

# HAVING
It filters groups after aggregation. It is used exactly like WHERE clause, but only with 'Group By'

# LIKE
This does pattern matching on text. 
% = zero or more characters, _ = exactly one character

# IN
It checks if a value matches any value in a given list 

# BETWEEN 
It checks if a value falls within a range and is inclusive on both ends.

---

# Primary Key
A primary key is a column that uniquely identifies a each row in a table. It is like a mix of unique and not null, and is used to find a particular row. Without this, you couldn't reliably update or delete a single record and could risk hitting multiple rows.

# Foreign Key
A foreign key is a column in one table that references the primary key of another table, creating a link between them. 

For example: If there is a table named- Customers, which have two columns: Cust_ID and Cust_Name, where Cust_ID is the primary key, AND another table named- Orders, which have two columns too: Cust_ID and Amount, then, Cust_ID acts as a foreign key between both the tables and link them.

---

# Relationships
It describes how rows in one table relates to rows of another table. The different kinds of relationships are:

- 1:1 (One to One): One row in Table A relates to one row in Table B- For a table User and another table Profile, each User has one Profile
- 1:M (One to Many): One row in Table A relates to many rows in Table B- For a table Department and another table Employee, one Department has many employees
- M:N (Many to Many): Many rows in Table A relates to many rows in Table B- It requires a bridge or junction table to join. If a student table has id and their name, course table has course id and course name, then a junction table is required which has student id and course id to relate both tables.

---

# Inner Join
It combines rows from two tables where there's a matching value in both (rows without a match in either table are excluded entirely). The common column is not a part of joined table.

# Left Join
LEFT JOIN (or LEFT OUTER JOIN) returns all rows from the left table, plus matching rows from the right table. If there's no match, right-table columns show NULL.

# Right Join
RIGHT JOIN is the mirror image of LEFT JOIN. It keeps all rows from the right table, with NULLs for unmatched left-table columns.

---


