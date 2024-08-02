# Commonly Asked DBMS Interview Questions and Answers

## 1. What are the advantages of DBMS over traditional file-based systems?
Database Management Systems (DBMS) were developed to address the following issues in traditional file-processing systems:
1. **Data Redundancy and Inconsistency**
2. **Difficulty in Accessing Data**
3. **Data Isolation** – multiple files and formats
4. **Integrity Problems**
5. **Atomicity of Updates**
6. **Concurrent Access by Multiple Users**
7. **Security Problems**

## 2. What are super, primary, candidate, and foreign keys?
- **Super Key**: A set of attributes that can uniquely identify a tuple in a relation.
- **Candidate Key**: A minimal superkey, no proper subset of which can be a superkey.
- **Primary Key**: A selected candidate key used to uniquely identify records in a table.
- **Foreign Key**: A field in one table that uniquely identifies a row of another table.

## 3. What is the difference between primary key and unique constraints?
- **Primary Key**: Cannot have NULL values and there is only one primary key per table.
- **Unique Constraints**: Can have NULL values and there can be multiple unique constraints per table.

## 4. What is database normalization?
Database normalization is the process of organizing data to minimize redundancy and improve data integrity. It involves decomposing tables to eliminate undesirable anomalies like insertion, deletion, and update anomalies.

## 5. Why is the use of DBMS recommended? Explain by listing some of its major advantages.
- **Controlled Redundancy**: Minimizes data duplication.
- **Data Sharing**: Multiple users can access data simultaneously.
- **Backup and Recovery**: Automates data backup and recovery.
- **Integrity Constraints**: Enforces data integrity.
- **Data Independence**: Changes to data structure do not affect application programs.

## 6. What are the differences between DDL, DML, and DCL in SQL?
- **DDL (Data Definition Language)**: Commands like CREATE, ALTER, DROP, TRUNCATE.
- **DML (Data Manipulation Language)**: Commands like SELECT, INSERT, DELETE, UPDATE.
- **DCL (Data Control Language)**: Commands like GRANT, REVOKE.

## 7. What is the difference between HAVING and WHERE clause?
- **WHERE Clause**: Filters rows before grouping; cannot contain aggregate functions.
- **HAVING Clause**: Filters groups after grouping; can contain aggregate functions.

## 8. How to print duplicate rows in a table?
Refer to the article on [How to Print Duplicate Rows in a Table](https://www.geeksforgeeks.org/how-to-print-duplicate-rows-in-a-table/).

## 9. What is Join?
A Join in SQL is used to combine rows from two or more tables based on a related column between them.

Example:
```sql
SELECT StudentCourse.CourseID, Student.StudentName
FROM StudentCourse
INNER JOIN Student ON StudentCourse.EnrollNo = Student.EnrollNo
ORDER BY StudentCourse.CourseID;
```

## 10. What is Identity?
Identity (or AutoNumber) is a column that automatically generates unique numeric values for new records.

## 11. What is a view in SQL? How to create a view?
A view is a virtual table based on the result-set of an SQL statement.
```sql
CREATE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition;
```

## 12. What are the uses of views?
- Limit exposure of underlying tables.
- Simplify complex queries.
- Act as aggregated tables.
- Hide complexity of data.
- Require little storage space.
- Provide additional security.

## 13. What is a Trigger?
A trigger is a set of SQL statements that automatically executes when an event occurs in the database, such as an INSERT, UPDATE, or DELETE operation.

## 14. What is a stored procedure?
A stored procedure is a precompiled collection of SQL statements stored in the database, used to perform a specific task.

## 15. What is the difference between Trigger and Stored Procedure?
Triggers automatically execute in response to events, while stored procedures must be explicitly called.

## 16. What is a transaction? What are ACID properties?
A transaction is a set of database operations that must be treated as a single unit. ACID properties ensure reliable processing:
- **Atomicity**
- **Consistency**
- **Isolation**
- **Durability**

## 17. What are indexes?
Indexes are data structures that improve the speed of data retrieval operations on a database table at the cost of additional writes and storage space.

## 18. What are clustered and non-clustered Indexes?
- **Clustered Index**: Data is stored physically in the order of the index.
- **Non-Clustered Index**: Logical ordering of data without affecting physical order.

## 19. What is Denormalization?
Denormalization is the process of adding redundancy to a database to improve read performance.

## 20. What is a CLAUSE in SQL?
A clause in SQL is a part of a query used to filter or customize the data retrieval process.

## 21. What is a Live Lock?
A livelock occurs when two or more processes continuously change states in response to each other without doing any useful work.

## 22. What is QBE (Query-by-Example)?
QBE is a visual approach for accessing information in a database by using query templates, allowing users to create queries by entering example values.

## 23. Why are cursors necessary in embedded SQL?
Cursors allow row-by-row processing of query results in embedded SQL, which operates on sets of data.

## 24. What is the purpose of normalization in DBMS?
Normalization reduces redundancy and database anomalies, divides large tables into smaller ones, and maintains data integrity.

## 25. What is the difference between a database schema and a database state?
- **Database Schema**: Overall design of the database.
- **Database State**: Collection of information stored in a database at a particular moment.

## 26. Explain the concepts of a Primary key and Foreign Key.
- **Primary Key**: Uniquely identifies records in a table.
- **Foreign Key**: Links two tables together, referencing the primary key of another table.

## 27. What are the main differences between Primary key and Unique Key?
- **Primary Key**: Cannot have NULL values; only one per table.
- **Unique Key**: Can have NULL values; multiple allowed per table.

## 28. What is the concept of sub-query in SQL?
A sub-query is a query within another query, used to retrieve data that will be used in the main query.

## 29. What is the use of the DROP command and what are the differences between DROP, TRUNCATE, and DELETE commands?
- **DROP**: Deletes a table and its structure permanently.
- **TRUNCATE**: Deletes all rows in a table, preserving the table structure.
- **DELETE**: Deletes specific rows in a table.

## 30. What is the main difference between UNION and UNION ALL?
- **UNION**: Combines data and removes duplicates.
- **UNION ALL**: Combines data without removing duplicates.

## 31. What is a Correlated Subquery in DBMS?
A subquery that is executed once for each row processed by the outer query.

## 32. Explain Entity, Entity Type, and Entity Set in DBMS.
- **Entity**: An object with a distinct existence in the real world.
- **Entity Type**: A collection of entities with the same attributes.
- **Entity Set**: A collection of entities of the same type.

## 33. What are the different levels of abstraction in DBMS?
- **Physical Level**: How data is stored.
- **Logical Level**: Type of data and relationships.
- **View Level**: Specific data views for users.

## 34. What integrity rules exist in DBMS?
- **Entity Integrity**: Primary key must be unique and not NULL.
- **Referential Integrity**: Foreign key must be NULL or match a primary key value in another table.

## 35. What is E-R model in DBMS?
The Entity-Relationship model is a conceptual framework for describing the structure of a database, including entities, attributes, and relationships.

## 36. What is a functional dependency in DBMS?
A relationship between attributes, where one attribute uniquely determines another attribute.

## 37. What is 1NF in DBMS?
First Normal Form (1NF) requires each table cell to contain only atomic (indivisible) values.

## 38. What is 2NF in DBMS?
Second Normal Form (2NF) is achieved when a table is in 1NF and all non-key attributes are fully dependent on the primary key.

## 39. What is 3NF in DBMS?
Third Normal Form (3NF) is achieved when a table is in 2NF and all non-key attributes are not transitively dependent on the primary key.

## 40. What is BCNF in DBMS?
Boyce-Codd Normal Form (BCNF) is a stricter version of 3NF, ensuring that for every functional dependency X->Y, X is a superkey.

## 41. What is a CLAUSE in SQL?
A clause in SQL is a part of a query that allows filtering or customizing data retrieval.

## 42. How can you get the alternate records from a table in SQL?
```sql
SELECT EmpId FROM (SELECT ROW_NUMBER() OVER (ORDER BY EmpId) AS rownum, EmpId FROM Emp) WHERE rownum % 2 = 1;
```

## 43. How is pattern matching done in SQL?
Pattern matching in SQL is

 done using the LIKE operator with '%' for multiple characters and '_' for a single character.
```sql
SELECT * FROM Emp WHERE name LIKE 'b%';
SELECT * FROM Emp WHERE name LIKE 'hans_';
```

## 44. What is a join in SQL?
A join is an SQL operation used to combine data from two or more tables based on a related column.

## 45. What are the different types of joins in SQL?
- **Inner Join**: Returns records with matching values in both tables.
- **Left Join**: Returns all records from the left table, and matched records from the right table.
- **Right Join**: Returns all records from the right table, and matched records from the left table.
- **Full Join**: Returns all records when there is a match in either table.

## 46. Explain the Stored Procedure.
A stored procedure is a group of SQL statements that perform a specific task, stored in the database.

## 47. What is RDBMS?
Relational Database Management System (RDBMS) stores data in tables and allows access based on relationships between tables.

## 48. What are the different types of relationships in DBMS?
- **One-to-One**
- **One-to-Many**
- **Many-to-Many**

## 49. What do you mean by Entity type extension?
Entity type extension is the grouping of similar entity types into a larger set.

## 50. What is conceptual design in DBMS?
Conceptual design is the first stage in database design, focusing on the high-level structure and relationships of data.

## 51. Differentiate between logical database design and physical database design. How does this separation lead to data independence?
- **Logical Database Design**: Focuses on the abstract structure of the database.
- **Physical Database Design**: Focuses on the actual storage of data.
This separation leads to data independence by allowing changes in physical storage without affecting logical structure.

## 52. What are temporary tables? When are they useful?
Temporary tables exist for the duration of a session or transaction. They are useful for storing intermediate results during complex queries.

## 53. Explain different types of failures that occur in the Oracle database.
- **Statement Failure**: Errors in SQL statements.
- **User Process Failure**: Abnormal disconnects or terminations.
- **User Error**: Data modification errors.
- **Instance Failure**: Failures due to power outages or software crashes.
- **Media Failure**: Hardware failures affecting storage.

## 54. What is the main goal of RAID technology?
RAID (Redundant Array of Independent Disks) combines multiple disks to improve fault tolerance and performance by distributing data across disks and providing redundancy.

## Conclusion
These DBMS interview questions and answers cover fundamental concepts and provide a solid foundation for preparing for DBMS-related interviews. For more in-depth knowledge, consider exploring advanced DBMS topics and practical applications.
