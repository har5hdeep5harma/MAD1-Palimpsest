# **Spreadsheets for Data Storage**

#### How Spreadsheets Help:

Spreadsheets are simple tools for storing tabular data and are often used in situations where complex databases may not be required. They consist of **rows** and **columns**, which makes them very similar to a **database table**.

Here’s what we can do with a spreadsheet:

-   **Organize Data**: Store student information in rows and columns.
    
-   **Perform Calculations**: Spreadsheets can calculate averages, sums, etc., over a range of cells (for example, calculating the average grade for each student).
    
-   **Use Multiple Sheets**: Spreadsheets allow you to store different sets of data on separate sheets, and these can be linked using common columns. For example, you can have one sheet for student data, one for course data, and another for relationships (enrollments).
    

#### Example: The Gradebook Spreadsheet

-   The **Students Table** might look like this (stored in one sheet):
    
    | Name | IDNumber | Address |
    | --- | --- | --- |
    | Sunil Shashi | MAD001 | Address 1 |
    | Chetana Anantha | MAD002 | Address 2 |
    | ... | ... | ... |
    
-   The **Courses Table** might look like this (stored in another sheet):
    
    | CourseID | CourseName |
    | --- | --- |
    | EE1001 | Introduction to Electrical Eng. |
    | AM1100 | Engineering Mechanics |
    | ... | ... |
    
-   The **Enrollment Table** links students to the courses they are registered for (another sheet):
    
    | StudentID | CourseID | Grade |
    | --- | --- | --- |
    | MAD001 | EE1001 | 85 |
    | MAD002 | AM1100 | 78 |
    | ... | ... | ... |
    

This setup avoids redundancy in the data and helps in maintaining consistency. In a larger application, such as in universities, using spreadsheets like this can be an efficient method for organizing small to medium amounts of data.

---

#### Limitations of Spreadsheets:

While spreadsheets are useful for smaller datasets, they have many **limitations**:

-   **Not Scalable**: As the data grows, spreadsheets become slow, prone to errors, and harder to manage.
    
-   **Limited Functionality**: Complex queries (like joining multiple tables or enforcing relationships) cannot be easily done in spreadsheets.
    
-   **Data Integrity**: Spreadsheets do not have built-in support for ensuring data integrity (like ensuring no duplicate student IDs or course IDs).
    

---

### **In-Memory Data Structures (Example in Python)**

**Python's in-memory data structures** are used to store the same information as above but without permanent storage.

#### Example in Python:

```python
# Data: Names, Courses, Relationships (student-course)
names = ['Alice', 'Bob', 'Charlie']
courses = ['Introduction to EE', 'Applied Mech', 'Calculus']
rels = [('Alice', 'Introduction to EE'),
        ('Bob', 'Calculus'),
        ('Alice', 'Calculus'),
        ('Charlie', 'Applied Mech')]
```

**Explanation**:

-   `names` is a list that stores student names.
    
-   `courses` is a list that stores course names.
    
-   `rels` is a list of tuples that stores relationships between students and courses they are enrolled in.
    

**Problem with In-memory Data**:

-   **Error-prone**: If you mistyped something (like a student's name or course name), the data might not be accurate, and it could lead to mistakes.
    
-   **Not Scalable**: Handling a large number of students and courses this way would be inefficient. The memory would be limited, and the program might slow down or crash with large amounts of data.
    
-   **Data Loss**: Since this data is stored in memory, once the program ends or the system is shut down, all this data is lost.
    
