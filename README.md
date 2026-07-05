
---

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




