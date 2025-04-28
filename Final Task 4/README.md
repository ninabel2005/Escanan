# Finals Task 4 - Employee Databases

---

## Task 1 - Query Statements (Problem 1)

**Objective:** Perform queries on the `EmployeeSalaries` table.

**Queries:**
```sql
-- List employee names and salaries ordered by salary (highest first)
SELECT employee_name, salary FROM EmployeeSalaries ORDER BY salary DESC;

-- Average salary per department
SELECT department, AVG(salary) AS average_salary FROM EmployeeSalaries GROUP BY department;
```

---

## Task 2 - Table Structure (Problem 1)

**Objective:** Create and populate the `payroll` database.

**Database Creation:**
```sql
CREATE DATABASE payroll;
USE payroll;

CREATE TABLE EmployeeSalaries (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    employee_name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10,2),
    hire_date DATE
);
```

**Sample Data Insertion:**
```sql
INSERT INTO EmployeeSalaries (employee_name, department, salary, hire_date) VALUES
('John Smith', 'Sales', 75000.00, '2017-05-15'),
('Jane Doe', 'Marketing', 85000.00, '2018-03-20'),
('Michael Johnson', 'Sales', 90000.00, '2016-08-10'),
('Emily Brown', 'HR', 65000.00, '2019-01-05'),
('David Wilson', 'Marketing', 80000.00, '2017-10-25'),
('Jennifer Lee', 'IT', 95000.00, '2015-06-30'),
('Christopher Davis', 'Sales', 70000.00, '2020-02-12'),
('Jessica Martinez', 'IT', 105000.00, '2014-09-18'),
('Andrew Taylor', 'Marketing', 75000.00, '2018-07-15'),
('Elizabeth Anderson', 'HR', 60000.00, '2020-04-01'),
('Daniel Thomas', 'IT', 98000.00, '2017-12-10'),
('Sarah White', 'Sales', 82000.00, '2019-08-05'),
('Kevin Garcia', 'HR', 70000.00, '2016-03-08'),
('Laura Martinez', 'Marketing', 88000.00, '2017-04-22'),
('Robert Lopez', 'IT', 93000.00, '2018-11-15'),
('Amanda Harris', 'Sales', 78000.00, '2018-09-30');
```

---

## Task 3 - Query Statements (Problem 2)

**Objective:** Perform queries on the `EmployeeData` table.

**Queries:**
```sql
-- List employee full names and salaries ordered by salary (highest first)
SELECT full_name, salary FROM EmployeeData ORDER BY salary DESC;

-- Average salary above 70,000
SELECT AVG(salary) AS average_salary FROM EmployeeData HAVING average_salary > 70000;

-- Employees with salary above 100,000
SELECT full_name FROM EmployeeData WHERE salary > 100000;

-- Count of employees
SELECT COUNT(employee_id) AS number_of_employees FROM EmployeeData;
```

---

## Task 4 - Table Structure (Problem 2)

**Objective:** Create and populate the `employeeDB` database.

**Database Creation:**
```sql
CREATE DATABASE employeeDB;
USE employeeDB;

CREATE TABLE EmployeeData (
    employee_id INT AUTO_INCREMENT PRIMARY KEY,
    full_name VARCHAR(100),
    department VARCHAR(50),
    salary DECIMAL(10,2),
    hire_date DATE,
    manager_id INT
);
```

**Sample Data Insertion:**
```sql
INSERT INTO EmployeeData (full_name, department, salary, hire_date, manager_id) VALUES
('John Smith', 'Sales', 75000.00, '2017-05-15', NULL),
('Jane Doe', 'Marketing', 85000.00, '2018-03-20', NULL),
('Michael Johnson', 'Sales', 90000.00, '2016-08-10', 1),
('Emily Brown', 'HR', 65000.00, '2019-01-05', NULL),
('David Wilson', 'Marketing', 80000.00, '2017-10-25', 2),
('Jennifer Lee', 'IT', 95000.00, '2015-06-30', NULL),
('Christopher Davis', 'Sales', 70000.00, '2020-02-12', 3),
('Jessica Martinez', 'IT', 105000.00, '2014-09-18', 6),
('Andrew Taylor', 'Marketing', 75000.00, '2018-07-15', 2),
('Elizabeth Anderson', 'HR', 60000.00, '2020-04-01', 4),
('Daniel Thomas', 'IT', 98000.00, '2017-12-10', 6),
('Sarah White', 'Sales', 82000.00, '2019-08-05', 1),
('Kevin Garcia', 'HR', 70000.00, '2016-03-08', 5),
('Laura Martinez', 'Marketing', 188000.00, '2017-04-22', 4),
('Robert Lopez', 'IT', 193000.00, '2018-11-15', 9),
('Amanda Harris', 'Sales', 128000.00, '2018-09-30', 1);
```

---

