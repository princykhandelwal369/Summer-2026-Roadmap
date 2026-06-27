# UPDATE

UPDATE table_name
SET column1 = value1, column2 = value2
WHERE condition;

Examples:
- UPDATE employees SET salary = 90000 WHERE name = 'Asha';
- UPDATE employees SET department = 'Engineering', salary = salary + 5000 WHERE department = 'R&D';
- UPDATE employees SET salary = salary * 1.10; (Here, without where, all employees salary will increase by 10%)

--- 

# DELETE

DELETE FROM table_name WHERE condition;
 
Examples:
- DELETE FROM employees WHERE department = 'HR';
- DELETE FROM employees WHERE salary < 20000;
- DELETE FROM employees; (deletes ALL rows, table itself still exists (empty).)

--- 

# ALTER TABLE

ALTER TABLE table_name ADD column_name datatype;
ALTER TABLE table_name DROP COLUMN column_name;
ALTER TABLE table_name MODIFY column_name new_datatype;   -- MySQL
ALTER TABLE table_name RENAME COLUMN old_name TO new_name;
ALTER TABLE table_name ADD CONSTRAINT constraint_name ...;

Examples:
- ALTER TABLE employees ADD email VARCHAR(100); (new column, existing rows get NULL there.)
- ALTER TABLE employees DROP COLUMN department;
- ALTER TABLE employees MODIFY salary DECIMAL(12,2); (change a column's data type/size.)

---

# AGGREGATE FUNCTIONS

SELECT COUNT(*) FROM table_name; (Returns total number of employees)
SELECT SUM(column) FROM table_name; (Returns sum of values in column)
SELECT AVG(column) FROM table_name; (Returns average of values in column)
SELECT MIN(column), MAX(column) FROM table_name; (Returns minimum and maximum value of column)

---

# GROUP BY

SELECT column, AGG_FUNC(other_column)
FROM table_name
GROUP BY column;

Examples:
- SELECT department, COUNT(*) FROM employees GROUP BY department;  (headcount per department)
- SELECT department, AVG(salary) FROM employees GROUP BY department; (average salary per department)
- SELECT department, city, COUNT(*) FROM employees GROUP BY department, city; (headcount per department+city combination)

---

# HAVING

SELECT column, AGG_FUNC(other_column)
FROM table_name
GROUP BY column
HAVING condition;

---

# LIKE

SELECT * FROM table_name WHERE column LIKE 'pattern';

Examples:
- WHERE name LIKE 'A%' (starts with A)
- WHERE name LIKE '%a' (ends with a)
- WHERE name LIKE '_o%' (second letter is 'o' -first char is anything, second is 'o', then anything after)

---

# IN

SELECT * FROM table_name WHERE column IN (value1, value2, value3);

Examples:
- WHERE department IN ('Sales', 'HR', 'Engineering'); (equivalent to dept='Sales' OR dept='HR' OR dept='Engineering')
- WHERE id NOT IN (1, 2, 3); (exclude specific ids)

---

# BETWEEN

SELECT * FROM table_name WHERE column BETWEEN low AND high;



