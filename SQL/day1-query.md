# Creating Database

CREATE DATABASE database_name; - This creates a new database in which we work
SHOW DATABASES;  - This will show all databases 
USE database_name; - This will switch into that database to be used
DROP DATABASE database_name; - This will delete the database
SELECT DATABASE(); - This will show which database is currently being used

# Creating table

CREATE TABLE table_name (
    column1 datatype constraints,
    column2 datatype constraints,
    ...
    PRIMARY KEY (column1)
);

OR

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    salary DECIMAL(10,2) DEFAULT 0,
    department VARCHAR(30)
);

# Inserting values

INSERT INTO table_name (col1, col2, col3)
VALUES (val1, val2, val3);

-- multiple rows at once
INSERT INTO table_name (col1, col2)
VALUES (v1, v2), (v3, v4), (v5, v6);

# SELECT

SELECT column1, column2 FROM table_name;
SELECT * FROM table_name;  - Selects all columns

# WHERE

SELECT * FROM table_name WHERE condition;
Examples:
- SELECT * FROM employees WHERE department = 'Engineering';
- SELECT * FROM employees WHERE salary BETWEEN 50000 AND 80000;
- SELECT * FROM employees WHERE department IN ('Sales', 'HR') AND salary > 40000;


# ORDER BY

SELECT * FROM table_name ORDER BY column1 (ASC or DESC);
SELECT * FROM table_name ORDER BY column1, column2 DESC;  -- multi-column sort
