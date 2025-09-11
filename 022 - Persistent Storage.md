# **Persistent Storage**

This is a critical concept for ensuring that data remains intact across system shutdowns and restarts. The example we are using is a **Gradebook**.

#### What is Persistent Storage?

Persistent storage refers to any form of data storage that keeps data even when the system is powered off. In the context of a **Gradebook**, the goal is to store student information (like name, ID) and course data (like course name, ID) in a way that survives a system restart.

**In-memory storage**, like variables or data structures (e.g., lists, dictionaries), only retains data while the system is running. Once the system is shut down, all that data is lost. Persistent storage, on the other hand, ensures that this data is saved permanently (or until the user decides to remove it).

#### Types of Persistent Storage:

1.  **File-Based Storage**: Simple files like CSV, Excel spreadsheets, or text files where data is saved to disk. However, these are not as efficient for handling complex relationships between data.
    
2.  **Database Storage**: Using **Relational Databases** (RDBMS) like MySQL, PostgreSQL, or SQLite to save data. These databases allow efficient handling of large datasets, complex queries, and maintain data integrity.
    
3.  **NoSQL Databases**: These are used for unstructured data and can be more flexible, but they often lack the validation rules and structure of relational databases.
    

#### In the Gradebook Example:

-   You have a set of **students** and a set of **courses**.
    
-   A **student** can be enrolled in multiple **courses** and vice versa. This is an example of a **many-to-many relationship**, where the relationships between entities are stored in a separate table to avoid redundancy.
    

#### How the Gradebook is Represented:

-   **Students Table**: Stores information about students, such as name, student ID, etc.
    
    -   Example: `StudentID, Name, Address, Phone Number`
        
-   **Courses Table**: Stores information about courses.
    
    -   Example: `CourseID, CourseName, Department`
        
-   **Enrollment Table**: Links students to courses using a **many-to-many** relationship. This table contains:
    
    -   `StudentID` (Foreign Key from Students Table)
        
    -   `CourseID` (Foreign Key from Courses Table)
        
    
    This way, if we have 100 students and 10 courses, we do not need to store each student's information repeatedly with each course they are enrolled in. Instead, we just record the student’s ID and the course ID in this linking table.
    

---

#### Why Do We Need Persistent Storage in This Case?

Without persistent storage, the data would disappear once the system is powered off or the program is closed. In the Gradebook example, you would lose student grades and course enrollments after each session. This is why we need **databases** or **spreadsheets** that store this information even if the computer is turned off.