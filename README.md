
## 🔹 MySQL Concepts & Theory Q&A

A collection of important MySQL interview questions and answers for quick revision and preparation.

**1. What is MySQL?**
MySQL is an open-source relational database management system (RDBMS) that uses SQL (Structured Query Language) to store, manage, and retrieve data. It is widely used due to its performance, scalability, reliability, and ease of integration with applications.


**2. What are the different types of JOINs in MySQL?**
- **INNER JOIN:** Returns rows with matching values in both tables.
- **LEFT (OUTER) JOIN:** Returns all rows from the left table and matched rows from the right.
- **RIGHT (OUTER) JOIN:** Returns all rows from the right table and matched rows from the left.
- **FULL OUTER JOIN:** Not directly supported in MySQL but can be achieved using UNION.

**3. What is the difference between WHERE and HAVING clauses?**
- **WHERE:** Filters rows before grouping.
- **HAVING:** Filters groups/aggregates after grouping.

**4. What is a Primary Key in MySQL?**
A Primary Key is a column (or set of columns) that uniquely identifies each record in a table.
- Must contain unique values.
- Cannot contain NULL.
- Each table can have only one primary key.

**5. What is a Foreign Key in MySQL?**
A Foreign Key is a field in one table that refers to the Primary Key in another table. It maintains referential integrity between tables.

**6. Difference between CHAR and VARCHAR**
- **CHAR:** Fixed-length storage. Pads with spaces if data is shorter. Faster for fixed-size data.
- **VARCHAR:** Variable-length storage. Saves only required characters. More memory efficient.

**7. Difference between DELETE, TRUNCATE, and DROP**
- **DELETE:** Removes rows based on condition, can be rolled back.
- **TRUNCATE:** Removes all rows, resets AUTO_INCREMENT, cannot usually be rolled back.
- **DROP:** Removes the entire table including structure. Permanent.

**8. What are Indexes in MySQL?**
Indexes are database objects that improve query performance by allowing faster lookups. Best used on columns in `WHERE`, `JOIN`, `ORDER BY`, `GROUP BY` clauses.

**9. What is a Transaction in MySQL?**
A Transaction is a sequence of operations executed as a single logical unit. It follows ACID properties:
- **Atomicity** – All or nothing
- **Consistency** – Valid state maintained
- **Isolation** – Independent transactions
- **Durability** – Changes persist after commit

**10. What is Normalization?**
Normalization is the process of structuring data to remove redundancy and improve integrity. Common forms: 1NF, 2NF, 3NF, BCNF.

**11. What is Denormalization?**
Denormalization combines tables to reduce joins and improve read performance. Increases redundancy intentionally for faster queries.

**12. What are Aggregate Functions in MySQL?**
- `COUNT()` – Number of rows
- `SUM()` – Adds values
- `AVG()` – Average value
- `MIN()` – Minimum value
- `MAX()` – Maximum value

**13. Difference between GROUP BY and ORDER BY**
- **GROUP BY:** Groups rows with identical values, used with aggregate functions.
- **ORDER BY:** Sorts query results (ascending or descending).

**14. AUTO_INCREMENT Attribute**
Automatically generates a sequential number for new records (commonly used with Primary Keys).

**15. UNION vs UNION ALL**
- **UNION:** Combines results and removes duplicate rows.
- **UNION ALL:** Combines results but keeps duplicates.

**16. Retrieve Current Date in MySQL**
```sql
SELECT CURDATE(); -- Returns current date
SELECT NOW();     -- Returns current date & time
```

**17. Difference between IN and EXISTS**
- **IN:** Checks if a value exists in a given list or subquery result.
- **EXISTS:** Checks if the subquery returns any rows (more efficient for large datasets).

**18. How do you create a table in MySQL?**
```sql
CREATE TABLE student (
  rollNo INT AUTO_INCREMENT PRIMARY KEY,
  name VARCHAR(100),
  marks INT
);
```

**19. TRIGGER vs STORED PROCEDURE**
- **TRIGGER:** Automatically invoked on specific table events (INSERT, UPDATE, DELETE).
- **STORED PROCEDURE:** Reusable code block, executes only when explicitly called.

**20. Handling NULL Values in MySQL**
- Use `IS NULL` / `IS NOT NULL` to check.
- `IFNULL(expr, default)` replaces NULLs with default.
- `COALESCE(expr1, expr2, …)` returns first non-null value.

**21. What is a View in MySQL?**
A View is a virtual table based on the result of a query.
- Does not store data itself.
- Provides abstraction, simplifies queries, improves security by exposing subsets of data.

**22. What are Storage Engines in MySQL?**
A Storage Engine determines how data is stored, retrieved, and indexed.
- **InnoDB:** Default engine. Supports transactions, foreign keys, and row-level locking.
- **MyISAM:** Faster for read-heavy workloads but no transaction support and uses table-level locking.

**23. What is the difference between Clustered and Non-Clustered Index?**
- **Clustered Index:** Determines the physical order of data in the table. A table can have only one (usually the Primary Key in InnoDB).
- **Non-Clustered Index:** A separate structure that points to the actual data. A table can have multiple.

**24. What is the difference between a Stored Procedure and a Stored Function?**
- **Stored Procedure:** Can perform actions (INSERT/UPDATE/DELETE), may or may not return a value, called with `CALL`.
- **Stored Function:** Must return a single value, can be used directly inside a SQL statement like `SELECT`.

**25. What are Window Functions in MySQL?**
Window functions perform calculations across a set of rows related to the current row, without collapsing them into a single result (unlike GROUP BY).
Examples: `ROW_NUMBER()`, `RANK()`, `DENSE_RANK()`, `LEAD()`, `LAG()`.
```sql
SELECT emp_name, salary,
RANK() OVER (ORDER BY salary DESC) AS salary_rank
FROM employees;
```

**26. What is the difference between Correlated and Non-Correlated Subquery?**
- **Non-Correlated Subquery:** Runs independently of the outer query; executes once.
- **Correlated Subquery:** References a column from the outer query; executes once per row of the outer query.

**27. What are Constraints in MySQL?**
Rules enforced on table columns to maintain data accuracy and integrity.
- `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, `FOREIGN KEY`, `CHECK`, `DEFAULT`

**28. What is Locking in MySQL?**
Locking prevents multiple transactions from corrupting data when accessing it simultaneously.
- **Row-level locking:** Locks only the affected row (InnoDB).
- **Table-level locking:** Locks the entire table (MyISAM).

**29. What is the difference between a View and a Materialized View?**
- **View:** Virtual table, data fetched live from the underlying query every time it's accessed.
- **Materialized View:** Stores the actual result physically (not natively supported in MySQL, but can be simulated with tables and scheduled events).

**30. What is Replication in MySQL?**
Replication copies data from one MySQL server (master) to one or more servers (replicas) to improve availability, scalability, and disaster recovery.

### ✅ Summary 
This section covers:
- Basic definitions
- Keys (Primary, Foreign)
- Joins, Aggregate functions, Transactions
- Normalization vs Denormalization
- Queries, Indexes, Views, Procedures
- Storage engines, Locking, Replication
- Window functions, Correlated subqueries, Constraints



# 📘 SQL Interview Questions & Answers (50 Qs)

A comprehensive list of Top 50 MySQL SQL Interview Questions & Answers.
This covers basic, intermediate, and advanced SQL queries frequently asked in technical interviews.

---

## 🔹 Section 1: Basic SQL Queries (1–15)

### 1. Select all records from a table

```sql
SELECT * FROM employees;
```

### 2. Fetch only unique department IDs

```sql
SELECT DISTINCT dept_id FROM employees;
```

### 3. Get number of employees

```sql
SELECT COUNT(*) FROM employees;
```

### 4. Fetch employee names and salaries

```sql
SELECT emp_name, salary FROM employees;
```

### 5. Employees earning more than 50,000

```sql
SELECT * FROM employees WHERE salary > 50000;
```

### 6. Employees joined after 2022-01-01

```sql
SELECT * FROM employees WHERE join_date > '2022-01-01';
```

### 7. Names starting with 'A'

```sql
SELECT * FROM employees WHERE emp_name LIKE 'A%';
```

### 8. Names ending with 'n'

```sql
SELECT * FROM employees WHERE emp_name LIKE '%n';
```

### 9. Sort salary descending

```sql
SELECT * FROM employees ORDER BY salary DESC;
```

### 10. Sort by department and name

```sql
SELECT * FROM employees ORDER BY dept_id, emp_name;
```

### 11. NULL manager check

```sql
SELECT * FROM employees WHERE manager_id IS NULL;
```

### 12. Replace NULL with 'N/A'

```sql
SELECT emp_name, IFNULL(manager_id, 'N/A') AS manager FROM employees;
```

### 13. First 5 employees

```sql
SELECT * FROM employees LIMIT 5;
```

### 14. Salary between range

```sql
SELECT * FROM employees WHERE salary BETWEEN 40000 AND 70000;
```

### 15. Employees in departments 1,2,3

```sql
SELECT * FROM employees WHERE dept_id IN (1,2,3);
```

---

## 🔹 Section 2: Aggregate Functions & GROUP BY (16–25)

### 16. Total salary

```sql
SELECT SUM(salary) FROM employees;
```

### 17. Average salary

```sql
SELECT AVG(salary) FROM employees;
```

### 18. Min & Max salary

```sql
SELECT MIN(salary), MAX(salary) FROM employees;
```

### 19. Employees per department

```sql
SELECT dept_id, COUNT(*) FROM employees GROUP BY dept_id;
```

### 20. Avg salary per department

```sql
SELECT dept_id, AVG(salary) FROM employees GROUP BY dept_id;
```

---

## 🔹 Section 3: Joins (26–35)

### 26. INNER JOIN

```sql
SELECT e.emp_name, d.dept_name
FROM employees e
INNER JOIN departments d ON e.dept_id = d.dept_id;
```

### 27. LEFT JOIN

```sql
SELECT e.emp_name, d.dept_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.dept_id;
```

### 28. RIGHT JOIN

```sql
SELECT e.emp_name, d.dept_name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.dept_id;
```

### 29. FULL JOIN

```sql
SELECT e.emp_name, d.dept_name
FROM employees e
LEFT JOIN departments d ON e.dept_id = d.dept_id
UNION
SELECT e.emp_name, d.dept_name
FROM employees e
RIGHT JOIN departments d ON e.dept_id = d.dept_id;
```

---

## 🔹 Section 4: Advanced Queries (36–50)

### 36. Second highest salary

```sql
SELECT MAX(salary)
FROM employees
WHERE salary < (SELECT MAX(salary) FROM employees);
```

### 38. Top 5 salaries

```sql
SELECT emp_name, salary
FROM employees
ORDER BY salary DESC
LIMIT 5;
```

### 41. Last 30 days employees

```sql
SELECT *
FROM employees
WHERE join_date >= CURDATE() - INTERVAL 30 DAY;
```

### 49. Highest salary employee

```sql
SELECT emp_name, salary
FROM employees
ORDER BY salary DESC
LIMIT 1;
```

---

## ✅ Summary

* Basic Queries: SELECT, WHERE, LIKE, LIMIT
* Aggregations: SUM, AVG, COUNT, GROUP BY
* Joins: INNER, LEFT, RIGHT, SELF JOIN
* Advanced: Subqueries, Ranking, Filtering




