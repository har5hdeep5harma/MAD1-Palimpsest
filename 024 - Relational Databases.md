# **Relational Databases (SQL)**

Relational databases store data in **tables** that have rows and columns. This allows us to structure data in a very organized way, ensuring easy access, manipulation, and relationships between various data entities.

#### **Basic Concepts of Relational Databases:**

1.  **Tables**:
    
    -   The core unit of a relational database is the **table**, which is like a spreadsheet.
        
    -   Each table stores data in **rows** and **columns**.
        
    -   Each row represents a record (an entry), and each column represents a **field** or **attribute** (like a student's name or ID).
        
    
    Example:
    
    -   **Students Table**:
        
        | StudentID | Name | Age | Address |
        | --- | --- | --- | --- |
        | 1 | Sunil Shashi | 20 | Address 1 |
        | 2 | Chetana Anantha | 21 | Address 2 |
        | 3 | Madhur Prakash | 22 | Address 3 |
        
2.  **Primary Key**:
    
    -   A **primary key** is a column (or a combination of columns) that uniquely identifies each row in a table.
        
    -   **Primary keys** must contain **unique values** and cannot contain **NULL values**.
        
    -   In the **Students Table**, the `StudentID` is the **Primary Key** because it uniquely identifies each student.
        
3.  **Foreign Key**:
    
    -   A **foreign key** is a column (or set of columns) in one table that links to the **primary key** of another table.
        
    -   Foreign keys are used to establish **relationships** between tables.
        
    
    Example:
    
    -   **Courses Table**:
        
        | CourseID | CourseName | Credits |
        | --- | --- | --- |
        | C101 | Introduction to EE | 3 |
        | C102 | Engineering Mechanics | 4 |
        | C103 | Functions of Several Variables | 3 |
        
    -   In the **Students Table**, we could add a column like `CourseID` that connects to the `CourseID` in the **Courses Table**. This would allow us to associate students with the courses they are enrolled in.
        
4.  **Relationships Between Tables**:
    
    -   **One-to-One Relationship**: Each record in Table A relates to exactly one record in Table B.
        
    -   **One-to-Many Relationship**: One record in Table A relates to many records in Table B. For example, one student can register for many courses, but each course only has one student.
        
    -   **Many-to-Many Relationship**: Many records in Table A can relate to many records in Table B. For example, students can be enrolled in many courses, and each course can have many students.
        

---

#### **Example 1: One-to-Many Relationship**

Consider the relationship between **Students** and **Courses**:

-   Each student can be enrolled in multiple courses, but each course has only one student at any given time.
    
-   To model this, we use a **StudentsCourses** table (linking table) to store which student is enrolled in which course.
    

**Students Table**:

| StudentID | Name | Age | Address |
| --- | --- | --- | --- |
| 1 | Sunil Shashi | 20 | Address 1 |
| 2 | Chetana Anantha | 21 | Address 2 |
| 3 | Madhur Prakash | 22 | Address 3 |

**Courses Table**:

| CourseID | CourseName | Credits |
| --- | --- | --- |
| C101 | Introduction to EE | 3 |
| C102 | Engineering Mechanics | 4 |
| C103 | Functions of Several Variables | 3 |

**StudentsCourses Table** (Many-to-Many Relationship):

| StudentID | CourseID |
| --- | --- |
| 1 | C101 |
| 1 | C102 |
| 2 | C103 |
| 3 | C102 |

In the **StudentsCourses Table**, each student can have multiple rows, each indicating a course they are enrolled in.

---

#### **Example 2: SQL Queries for Data Retrieval**

**SELECT Query**:  
SQL queries allow you to retrieve data from one or more tables. The most common type is the **SELECT** query.

**Example 1: Find All Students**:

```sql
SELECT Name, Age, Address FROM Students;
```

This query retrieves the **Name**, **Age**, and **Address** of all students in the **Students Table**.

**Example 2: Find All Students in a Specific Course**:  
To find all students enrolled in the **"Introduction to EE"** course, we need to join the **Students** and **StudentsCourses** tables based on the **StudentID**:

```sql
SELECT s.Name
FROM Students s
JOIN StudentsCourses sc ON s.StudentID = sc.StudentID
JOIN Courses c ON c.CourseID = sc.CourseID
WHERE c.CourseName = 'Introduction to EE';
```

-   This query uses an **INNER JOIN** to link the **Students** table, the **StudentsCourses** table, and the **Courses** table.
    
-   We are looking for students whose course name is 'Introduction to EE'.
    

---

### **Important SQL Operations:**

1.  **JOIN**:
    
    -   **INNER JOIN**: Combines rows from two or more tables where there is a match in both tables.
        
    -   **LEFT JOIN (or LEFT OUTER JOIN)**: Returns all records from the left table and matched records from the right table. If there is no match, `NULL` values are returned for columns from the right table.
        
    
    Example of **LEFT JOIN**:
    
    ```sql
    SELECT s.Name, c.CourseName
    FROM Students s
    LEFT JOIN StudentsCourses sc ON s.StudentID = sc.StudentID
    LEFT JOIN Courses c ON c.CourseID = sc.CourseID;
    ```
    
    This would list all students and the courses they are enrolled in, including students who are not enrolled in any course (the course name would be `NULL`).
    
2.  **WHERE Clause**:
    
    -   Used to filter records based on certain conditions.
        
    -   Example: `WHERE Age > 20` to find all students older than 20.
        
3.  **GROUP BY**:
    
    -   Used to group rows that have the same values into summary rows, often used with aggregate functions like `COUNT()`, `AVG()`, `SUM()`.
        
    
    Example: To count how many students are enrolled in each course:
    
    ```sql
    SELECT c.CourseName, COUNT(sc.StudentID) AS NumberOfStudents
    FROM Courses c
    LEFT JOIN StudentsCourses sc ON c.CourseID = sc.CourseID
    GROUP BY c.CourseName;
    ```
    
4.  **INSERT, UPDATE, DELETE**:
    
    -   **INSERT**: Adds new records to a table.
        
        ```sql
        INSERT INTO Students (StudentID, Name, Age, Address) 
        VALUES (4, 'Raghav Sharma', 23, 'Address 4');
        ```
        
    -   **UPDATE**: Modifies existing records.
        
        ```sql
        UPDATE Students SET Address = 'New Address' WHERE StudentID = 1;
        ```
        
    -   **DELETE**: Removes records from a table.
        
        ```sql
        DELETE FROM Students WHERE StudentID = 4;
        ```
        
---

#### **Normalization**:

-   This is a process of organizing data to reduce redundancy and improve data integrity.
    
-   **First Normal Form (1NF)**: Ensures each column contains only atomic (indivisible) values, and each record is unique.
    
-   **Second Normal Form (2NF)**: Achieved by removing partial dependencies (when non-key attributes depend on only part of the primary key).
    
-   **Third Normal Form (3NF)**: Ensures that no transitive dependencies exist (non-key attributes should not depend on other non-key attributes).