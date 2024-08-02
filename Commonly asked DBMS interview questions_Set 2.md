# Commonly Asked DBMS Interview Questions | Set 2

## 1. Query to find the repeated row in a table
Given the table:

| Name | Section |
|------|---------|
| abc  | CS1     |
| bcd  | CS2     |
| abc  | CS1     |

To find the duplicate row:
```sql
SELECT name, section 
FROM tbl
GROUP BY name, section
HAVING COUNT(*) > 1;
```

## 2. Query to find the 2nd highest salary of an employee
```sql
SELECT MAX(salary) 
FROM EMPLOYEES 
WHERE salary < (SELECT MAX(salary) FROM EMPLOYEES);
```
Or
```sql
SELECT MAX(salary) 
FROM EMPLOYEES 
WHERE salary IN (SELECT salary FROM EMPLOYEES MINUS SELECT MAX(salary) FROM EMPLOYEES);
```

## 3. Number of rows in the result of the given query
Given the Employee table:

| ID | salary | DeptName |
|----|--------|----------|
| 1  | 10000  | EC       |
| 2  | 40000  | EC       |
| 3  | 30000  | CS       |
| 4  | 40000  | ME       |
| 5  | 50000  | ME       |
| 6  | 60000  | ME       |
| 7  | 70000  | CS       |

The query:
```sql
SELECT E.ID
FROM Employee E
WHERE EXISTS (SELECT E2.salary
              FROM Employee E2
              WHERE E2.DeptName = 'CS'
              AND E.salary > E2.salary);
```
The result will be 5 rows: 2, 4, 5, 6, 7.

## 4. Trigger to update Emp table after an update in Dep table
```sql
CREATE OR REPLACE TRIGGER update_trig
AFTER UPDATE ON Dept
FOR EACH ROW
DECLARE
    CURSOR emp_cur IS SELECT * FROM Emp;
BEGIN
    FOR i IN emp_cur LOOP
        IF i.dept_no = :NEW.dept_no THEN
            DBMS_OUTPUT.PUT_LINE(i.emp_no);  -- for printing those emp numbers which are updated
            UPDATE Emp
            SET sal = i.sal + 100
            WHERE emp_no = i.emp_no;
        END IF;
    END LOOP;
END;
```

## 5. Query to find students with marks greater than average marks
```sql
SELECT student, marks 
FROM table
WHERE marks > (SELECT AVG(marks) FROM table);
```

## 6. Query to find the employee with the third-highest salary
```sql
SELECT Emp1.Name
FROM Employee Emp1
WHERE 2 = (SELECT COUNT(DISTINCT(Emp2.Salary))
           FROM Employee Emp2
           WHERE Emp2.Salary > Emp1.Salary);
```

## 7. Why can't we use WHERE clause with aggregate functions like HAVING?
The WHERE clause filters rows before any groupings are made, while the HAVING clause filters rows after groupings are made. The WHERE clause works on individual rows of data, not on aggregated data.

Example:
```sql
SELECT Student, SUM(Score) AS total 
FROM Marks
GROUP BY Student
HAVING SUM(Score) > 70;
```

## 8. Difference between primary key and unique key
- **Primary Key**:
  - Only one per table.
  - Cannot have NULL values.
  - Uniquely identifies a row.
- **Unique Key**:
  - Can be multiple per table.
  - Can have one NULL value.
  - Ensures uniqueness for a column or set of columns.

## 9. Difference between materialized and dynamic view
- **Materialized View**:
  - Stored on disk and updated periodically.
  - Requires synchronization with base tables.
- **Dynamic View**:
  - Virtual, runs query definition each time accessed.
  - Created dynamically when requested by the user.

## 10. What is embedded and dynamic SQL?
- **Embedded SQL**:
  - SQL statements are hard-coded into the application.
  - Static and predetermined at compile time.
- **Dynamic SQL**:
  - SQL statements are constructed at runtime.
  - Allows for flexible and general-purpose applications.

## 11. Difference between CHAR and VARCHAR
- **CHAR**:
  - Fixed-length.
  - Maximum 255 characters.
  - Faster retrieval.
  - Static memory allocation.
- **VARCHAR**:
  - Variable-length.
  - Maximum 4000 characters.
  - Slower retrieval.
  - Dynamic memory allocation.

## Conclusion
These commonly asked DBMS interview questions cover various aspects of database management, including SQL queries, database design, and concepts such as triggers, normalization, and different SQL clauses. Understanding these questions will help you prepare for technical interviews and demonstrate your proficiency in database management systems.
