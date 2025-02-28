# Basic SQL `CREATE TABLE` Statement

## **Introduction**
The `CREATE TABLE` statement is used to define a **new table** in SQL, specifying its **columns, data types, and constraints**.

## **Syntax**
A basic `CREATE TABLE` statement follows this structure:

```sql
CREATE TABLE TableName (
    ColumnName1 DataType [Constraint],
    ColumnName2 DataType [Constraint],
    ...
    [CONSTRAINT ConstraintName <Constraint-spec>]
);
```

## **Column List with Data Types and Constraints**
Each column must have:
- A **name**.
- A **data type** (e.g., `VARCHAR`, `INT`).
- **Optional constraints** to enforce rules.

Constraints can be **inline** (specified within the column definition) or **external** (defined at the end).

## **Common Constraints**
| Constraint | Description |
|------------|-------------|
| **`PRIMARY KEY (PK)`** | Ensures a column (or combination) has unique, non-null values. |
| **`FOREIGN KEY (FK)`** | Links a column to a primary key in another table. |
| **`UNIQUE`** | Ensures column values are unique but allows NULLs. |
| **`CHECK`** | Restricts column values based on a condition. |

---

## **Example: Student and Enrollment Tables**
This example includes:
- **Primary Key (`PK`)** for unique student identification.
- **Foreign Key (`FK`)** to link enrollments to students.

```sql
CREATE TABLE Students (
    StdNo          CHAR(11) PRIMARY KEY,
    StdFirstName   VARCHAR(45) NOT NULL,
    StdLastName    VARCHAR(45),
    BirthDate      DATE,
    Email          VARCHAR(100) UNIQUE
);

CREATE TABLE Enrollment (
    EnrollmentID   INT PRIMARY KEY,
    StdNo          CHAR(11),
    CourseCode     VARCHAR(10) NOT NULL,
    Semester       VARCHAR(10) CHECK (Semester IN ('Fall', 'Spring', 'Summer')),
    Grade          CHAR(2),

    -- Define Foreign Key
    CONSTRAINT fk_student FOREIGN KEY (StdNo) REFERENCES Students(StdNo) 
        ON DELETE CASCADE ON UPDATE CASCADE
);
```

### **Students Table**
| **StdNo** (PK) | **StdFirstName** | **StdLastName** | **BirthDate** | **Email** (Unique) |
|---------------|-----------------|----------------|-------------|----------------|
| CHAR(11)     | VARCHAR(45) (NOT NULL) | VARCHAR(45) | DATE        | VARCHAR(100) (Unique) |

### **Enrollment Table**
| **EnrollmentID** (PK) | **StdNo** (FK) | **CourseCode** | **Semester** (CHECK) | **Grade** |
|------------------|---------------|-------------|------------------|--------|
| INT (Primary Key) | CHAR(11) (Foreign Key) | VARCHAR(10) (NOT NULL) | 'Fall', 'Spring', 'Summer' | CHAR(2) |
### **Key Takeaways from the Example**
✔ **`PRIMARY KEY`**: Ensures unique identification for both `Students` and `Enrollment`.  
✔ **`FOREIGN KEY`**: Links `StdNo` in `Enrollment` to `StdNo` in `Students`.  
✔ **`CHECK` Constraint**: Restricts `Semester` values to valid options.  
✔ **`UNIQUE` Constraint**: Ensures each student has a unique email.  
✔ **`ON DELETE CASCADE`**: Deletes enrollments if a student record is removed.  

---

## **Importance of Proper Syntax**
❌ A **missing comma** can cause syntax errors.  

**Common SQL Syntax Errors:**
- **Incorrect spelling** of SQL keywords (`Creat Table` instead of `CREATE TABLE`).
- **Forgetting commas** between column definitions.
- **Missing parentheses** in constraints.

**Example of a syntax mistake:**
```sql
CREATE TABLE Students (
     StdNo CHAR(11) PRIMARY KEY
     StdFirstName VARCHAR(45),  -- ❌ Missing comma here!
     BirthDate DATE
 );
 ```
 **Error:** The database does not recognize `StdFirstName` because the previous line lacks a comma.

---

## **Common SQL Data Types**
| Data Type | Description |
|-----------|------------|
| **`CHAR(n)`** | Fixed-length string (`n` characters). |
| **`VARCHAR(n)`** | Variable-length string (up to `n` characters). |
| **`INT`** | Integer values. |
| **`FLOAT`** | Approximate decimal values. |
| **`DECIMAL(p, s)`** | Precise decimal values (`p` total digits, `s` decimal places). |
| **`DATE`** | Stores dates (`YYYY-MM-DD`). |
| **`TIME`** | Stores time (`HH:MM:SS`). |
| **`TIMESTAMP`** | Stores both date and time (`YYYY-MM-DD HH:MM:SS`). |

---

## **Summary**
- The `CREATE TABLE` statement **defines** a table’s structure.
- **Constraints** ensure data integrity.
- **Proper syntax** prevents errors.
- **Common data types** determine how data is stored.

🚀 **Next Lesson: Inserting and Retrieving Data (`INSERT` and `SELECT` Statements)!**
```

This version is **clean, structured, and easy to follow**, making it more **engaging and informative**. Let me know if you want any modifications! 🚀