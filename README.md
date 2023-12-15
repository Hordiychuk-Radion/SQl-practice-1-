# SQl-practice-1-
```
CREATE TABLE EmployeeData (
    EmployeeID INT PRIMARY KEY,
    FirstName NVARCHAR(50),
    LastName NVARCHAR(50),
    Department NVARCHAR(50),
    Salary DECIMAL(10, 2)
);

INSERT INTO EmployeeData VALUES
(1, 'John', 'Doe', 'IT', 60000.00),
(2, 'Jane', 'Smith', 'HR', 55000.00),
(3, 'Bob', 'Johnson', 'Finance', 70000.00),
(4, 'Alice', 'Williams', 'Marketing', 58000.00),
(5, 'Charlie', 'Brown', 'IT', 62000.00);
```


**Select All Employees**
```
SELECT * FROM EmployeeData;
```
**Filter by Department (e.g., IT)**
```
SELECT * FROM EmployeeData WHERE Department = 'IT';
```
**Order by Salary (Descending)**
```
SELECT * FROM EmployeeData ORDER BY Salary DESC;
```
**Calculate Average Salary**
```
SELECT AVG(Salary) AS AverageSalary FROM EmployeeData;
```
**Count Employees in Each Department**
```
SELECT Department, COUNT(*) AS EmployeeCount FROM EmployeeData GROUP BY Department;
```
**Find Highest Salary in Each Department**
```
SELECT Department, MAX(Salary) AS HighestSalary FROM EmployeeData GROUP BY Department;
```
**Update Salary for a Specific Employee (e.g., EmployeeID = 2)**
```
UPDATE EmployeeData
SET Salary = 43000
WHERE EmployeeID = 2;
```

**Insert a New Employee**
```
INSERT INTO EmployeeData (EmployeeID, FirstName, LastName, Department, Salary) VALUES (6, 'New', 'Employee', 'Finance', 65000.00);
```
**Delete an Employee (e.g., EmployeeID = 4)**
DELETE FROM EmployeeData WHERE EmployeeID = 4;

**Find Employees with Salaries above Average**
```
SELECT * FROM EmployeeData WHERE Salary > (SELECT AVG(Salary) FROM EmployeeData);
```

**Calculate Total Salary Expense for Each Department**
```
SELECT Department, SUM(Salary) AS TotalSalaryExpense
FROM EmployeeData
GROUP BY Department;
```
