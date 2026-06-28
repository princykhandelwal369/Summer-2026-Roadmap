# Primary Key

CREATE TABLE employees (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(50)
);

# Foreign Key

CREATE TABLE orders (
    id INT PRIMARY KEY,
    customer_id INT,
    amount DECIMAL(10,2),
    FOREIGN KEY (customer_id) REFERENCES customers(id)
);

# Inner Join

SELECT customers.name, orders.id AS order_id
FROM customers
INNER JOIN orders ON customers.id = orders.customer_id;

Examples:
- SELECT e.name, d.name AS dept_name FROM employees e INNER JOIN departments d ON e.department_id = d.id;
- SELECT o.id, c.name FROM orders o INNER JOIN customers c ON o.customer_id = c.id WHERE o.amount > 100;

# Left Join

SELECT c.name, o.id AS order_id
FROM customers c
LEFT JOIN orders o ON c.id = o.customer_id;

---