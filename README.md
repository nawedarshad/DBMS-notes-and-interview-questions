# DBMS-notes-and-interview-questions

# SQL Notes and Interview Questions

## Introduction
SQL (Structured Query Language) is a standard database language used for accessing and manipulating data in databases. Developed by IBM Computer Scientists in the 1970s, SQL allows for the creation, update, deletion, and retrieval of data in databases like MySQL, Oracle, PostgreSQL, etc. This document covers 70+ SQL interview questions with answers, helping freshers and experienced professionals prepare for SQL developer interviews at MAANG and other high-paying companies.

## Basic SQL Interview Questions and Answers

### 1. What is SQL?
SQL stands for Structured Query Language. It is used to interact with databases to create databases, tables, retrieve data, update tables, and more. SQL is an ANSI standard.

### 2. What is a Database?
A Database is a structured form of data storage in a computer or a collection of data in an organized manner. It includes schemas, tables, queries, views, etc., and allows for easy storage, access, and manipulation of data.

### 3. Does SQL support programming language features?
SQL is a command language, not a programming language. It lacks conditional statements like loops or if..else. SQL is used for querying, updating, deleting data, etc.

### 4. What is the difference between CHAR and VARCHAR2 datatype in SQL?
- **CHAR**: Used for character strings of fixed length.
- **VARCHAR2**: Used for character strings of variable length.

### 5. What do you mean by data definition language?
Data Definition Language (DDL) allows execution of queries like CREATE, DROP, and ALTER, which define the data.

### 6. What do you mean by data manipulation language?
Data Manipulation Language (DML) is used to access or manipulate data in the database. It includes:
- Insert data
- Delete data
- Retrieve data
- Update data

### 7. What is a view in SQL?
A view is a virtual table in SQL. It can be created by selecting fields from one or more tables in the database. 

```sql
CREATE VIEW view_name AS
SELECT column1, column2...
FROM table_name
WHERE condition;
```

### 8. What do you mean by foreign key?
A foreign key is a field that uniquely identifies each row in another table, creating a link between the two tables.

```sql
CREATE TABLE Orders (
  O_ID int NOT NULL,
  ORDER_NO int NOT NULL,
  C_ID int,
  PRIMARY KEY (O_ID),
  FOREIGN KEY (C_ID) REFERENCES Customers(C_ID)
);
```

### 9. What are table and field?
- **Table**: Combination of rows (records) and columns (fields).
- **Field**: A single piece of information from a record in a database.

### 10. What is the primary key?
A Primary Key uniquely identifies each row in a table. There can only be one primary key in a table.

### 11. What is a Default constraint?
The DEFAULT constraint fills a column with default values when no other value is provided.

### 12. What is normalization?
Normalization is the process of organizing data to minimize redundancy and avoid insertion, deletion, and update anomalies.

### 13. What is denormalization?
Denormalization is a database optimization technique where redundant data is added to one or more tables to avoid costly joins in a normalized database.

### 14. What is a query?
An SQL query retrieves the required data from the database.

### 15. What is a subquery?
A subquery is a query within another query, embedded in the WHERE clause.

### 16. What are the different operators available in SQL?
1. Arithmetic Operators
2. Logical Operators
3. Comparison Operators

### 17. What is a constraint?
Constraints are rules applied to the type of data in a table to specify limits on the type of data stored in a particular column.

### 18. What is Data Integrity?
Data integrity ensures that data in the database is both correct and consistent.

### 19. What is Auto Increment?
Auto Increment automatically generates a numerical primary key value for every new record inserted.

### 20. What is MySQL collation?
MySQL collation is a set of rules used to compare characters of a particular character set using their encoding.

### 21. What are user-defined functions?
User-defined functions in PL/SQL or Java provide functionality not available in SQL or SQL built-in functions.

### 22. What are all types of user-defined functions?
1. Scalar User-Defined Function
2. Inline Table-Value User-Defined Function
3. Multi-Statement Table-Value User-Defined Function

### 23. What is a stored procedure?
Stored Procedures are groups of SQL statements that accept input parameters and perform tasks, potentially returning values.

### 24. What are aggregate and scalar functions?
- **Aggregate Functions**: Perform operations on values of a column and return a single value.
- **Scalar Functions**: Perform operations based on user input and return a single value.

### 25. What is an ALIAS command?
Aliases are temporary names given to a table or column for a particular SQL query.

### 26. What are Union, Minus, and Intersect commands?
Set operations in SQL that eliminate duplicate tuples and apply only to union-compatible relations.

### 27. What is T-SQL?
T-SQL (Transact-SQL) is an extension of SQL used to interact with relational databases, primarily with Microsoft SQL servers.

### 28. What is ETL in SQL?
ETL stands for Extract, Transform, and Load. It is a process in Data Warehousing to pull data from one database and put it into another.

### 29. How to copy tables in SQL?
```sql
CREATE TABLE ContactList(Clone_1) LIKE Original_table;
```

### 30. What is SQL injection?
SQL injection exploits user data through web page inputs by injecting SQL commands as statements.

### 31. Can we disable a trigger?
Yes, using the `ALTER TRIGGER` statement with the `DISABLE` option.

## Intermediate SQL Interview Questions and Answers

### 32. What are the differences between SQL and PL/SQL?
- **SQL**: Query execution or commanding language, data-oriented, declarative.
- **PL/SQL**: Complete programming language, procedural, used for creating applications.

### 33. What is the difference between BETWEEN and IN operators in SQL?
- **BETWEEN**: Fetch rows based on a range of values.
- **IN**: Check for values contained in specific sets.

### 34. Write an SQL query to find the names of employees starting with ‘A’.
```sql
SELECT * FROM Employees WHERE EmpName LIKE 'A%';
```

### 35. What is the difference between primary key and unique constraints?
- **Primary Key**: Cannot have NULL values, one per table, creates a clustered index.
- **Unique Constraints**: Can have NULL values, multiple per table, does not create a clustered index.

### 36. What is a join in SQL? What are the types of joins?
SQL Join combines data or rows from two or more tables based on a common field.
- **INNER JOIN**
- **LEFT JOIN**
- **RIGHT JOIN**
- **FULL JOIN**

### 37. What is an index?
A database index is a data structure that improves the speed of data retrieval operations on a database table.

### 38. What is the On Delete cascade constraint?
`ON DELETE CASCADE` automatically deletes rows in the child table when rows in the parent table are deleted.

### 39. Explain the WITH clause in SQL?
The WITH clause defines a temporary relation whose definition is available only to the query in which the WITH clause occurs.

### 40. What are all the different attributes of indexes?
- **Access Types**
- **Access Time**
- **Insertion Time**
- **Deletion Time**
- **Space Overhead**

### 41. What is a Cursor?
A cursor is a temporary memory or work station allocated by the database server for performing DML operations on a table.

### 42. Write down various types of relationships in SQL?
1. One-to-One Relationship
2. One-to-Many Relationship
3. Many-to-One Relationship
4. Self-Referencing Relationship

### 43. What is a trigger?
A trigger is a statement executed automatically when there is any modification to the database.

### 44. What is the difference between SQL DELETE and SQL TRUNCATE commands?
- **DELETE**: Removes rows one at a time, slower, retains table space, uses DELETE permission.
- **TRUNCATE**: Deallocates data pages, faster, resets identity column, uses ALTER permission.

### 45. What is the difference between Cluster and Non-Cluster Index?
- **Clustered Index**: Faster, requires less memory, one per table, stores pointers to blocks.
- **Non-Clustered Index**: Slower, requires more memory, multiple per table, stores values and pointers.

### 46. What is a Live Lock?
Live lock occurs when processes continually repeat the same interaction without doing useful work, unlike a deadlock where all processes are in a waiting state.

### 47. What is Case WHEN in SQL?
The CASE statement handles if/then logic.

```sql
CASE case_value 
  WHEN when_value THEN statement_list 
  [WHEN when_value THEN statement_list] … 
  [ELSE statement_list]
END CASE
```

## Advanced SQL Interview Questions and Answers

### 48. Name different types of case manipulation functions available in SQL.
1. **LOWER**: Converts string to lowercase.
2. **UPPER**: Converts string to uppercase.
3. **INITCAP**: Converts the first letter to uppercase and the rest to lowercase.

### 49. What are local and global variables and their differences?
- **Global Variable

**: Defined outside functions, global scope.
- **Local Variable**: Defined within functions, local scope.

### 50. Name the function which is used to remove spaces at the end of a string?
```sql
TRIM(s);
```

### 51. What is the difference between TRUNCATE and DROP statements?
- **DROP**: Removes table definition and contents, frees table space.
- **TRUNCATE**: Deletes all rows, does not free table space.

### 52. Which operator is used in queries for pattern matching?
```sql
SELECT column1, column2 
FROM table_name 
WHERE column_name LIKE pattern;
```

### 53. Define SQL Order by the statement?
The ORDER BY statement sorts the fetched data in ascending or descending order.

### 54. Explain SQL Having statement?
The HAVING clause specifies a condition for a group or aggregate function used in the select statement.

### 55. Explain SQL AND OR statement with an example?
- **AND Operator**: Displays records where both conditions are true.
- **OR Operator**: Displays records where either condition is true.

### 56. Define BETWEEN statements in SQL?
Tests if an expression is within a range of values.

### 57. Why do we use Commit and Rollback commands?
- **COMMIT**: Permanently saves changes.
- **ROLLBACK**: Undoes changes made by the current transaction.

### 58. What are ACID properties?
ACID properties (Atomicity, Consistency, Isolation, Durability) guarantee reliable processing of database transactions.

### 59. Are NULL values the same as zero or a blank space?
No, NULL values are not the same as zero or a blank space.

### 60. What is the need for group functions in SQL?
Group functions (aggregate functions) group values of multiple rows to form a single value.

### 61. What is the need for a MERGE statement?
The MERGE statement combines INSERT, UPDATE, and DELETE operations into one statement.

### 62. How can you fetch common records from two tables?
```sql
SELECT table1.column1, table2.column2 
FROM table1
JOIN table2
ON table1.column = table2.column
ORDER BY column;
```

### 63. What are the advantages of PL/SQL functions?
- Single call to the database
- Code manageability and readability
- Reusability
- Security and data hiding

### 64. What is the SQL query to display the current date?
```sql
SELECT CURRENT_DATE;
```

### 65. What are Nested Triggers?
Triggers that contain INSERT, UPDATE, and DELETE logic within themselves, causing other triggers to fire.

### 66. How to find the available constraint information in the table?
Use data dictionary tables in SQL Server.

### 67. How do we avoid getting duplicate entries in a query without using the DISTINCT keyword?
- Use row numbers
- Use self-Join
- Use GROUP BY

### 68. The difference between NVL and NVL2 functions?
- **NVL(expr1, expr2)**: Converts a null value to an actual value.
- **NVL2(expr1, expr2, expr3)**: Returns expr2 if expr1 is not null, else returns expr3.

### 69. What is the difference between COALESCE() & ISNULL()?
- **COALESCE()**: Returns the first non-NULL expression among its arguments.
- **ISNULL()**: Replaces NULL values.

### 70. Name the operator which is used in the query for appending two strings?
The Concatenation operator (`||`) is used to append two strings.

## Conclusion
Mastering SQL interview questions is crucial for data analysts, data engineers, and business analysts. Understanding and practicing these questions enhances your ability to tackle SQL-related interview challenges effectively. Each question is an opportunity to demonstrate your analytical prowess and technical expertise, essential traits for any aspiring professional in these critical roles.
