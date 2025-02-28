# Integrity Constraint Syntax

## **Why Are Constraint Names Important?**
- Imagine being a **database administrator (DBA)** handling an error with a meaningless error name.
- A well-named **constraint** helps in debugging and resolving violations efficiently.


## **Types of Constraints in SQL**
| Constraint Type | Description |
|---------------|-------------|
| **Primary Key (PK)** | Ensures a column (or combination) has **unique, non-null values**, behave as "unique identity" of a row |
| **Foreign Key (FK)** | Establishes a **relationship** between two tables |
| **Unique** | Ensures all values in a column (or combination) are **unique** |
| **Required (NOT NULL)** | Ensures a column **cannot be NULL** |
| **Check** | Ensures column values **meet a specified condition** |

---

## **Constraint Placement in SQL**
- **Inline** Constraints: Defined inside the column definition.
- **External** Constraints: Defined after all columns.

```sql
CREATE TABLE Students (
    StdNo          CHAR(11) PRIMARY KEY,  -- Inline PK
    StdFirstName   VARCHAR(45) NOT NULL,  -- Required
    StdLastName    VARCHAR(45),
    BirthDate      DATE,
    Email          VARCHAR(100) UNIQUE    -- Unique
);
```

### **Example: External Constraints**
- Used for **multi-column constraints** (e.g., composite keys, FK references).

```sql
CREATE TABLE Enrollment (
    EnrollmentID   INT,
    StdNo          CHAR(11),
    CourseCode     VARCHAR(10) NOT NULL,
    Semester       VARCHAR(10),
    Grade          CHAR(2),

    -- External Constraints
    CONSTRAINT pk_enrollment PRIMARY KEY (EnrollmentID),
    CONSTRAINT fk_student FOREIGN KEY (StdNo) REFERENCES Students(StdNo) 
        ON DELETE CASCADE ON UPDATE CASCADE
);
```

---

## **Primary Key Constraints**
A **primary key (PK)** ensures:
1. **Uniqueness** - No duplicate values.
2. **Non-nullability** - No `NULL` values.

#### **Examples**
```sql
-- Single-column PK (Inline)
CREATE TABLE Courses (
    CourseCode VARCHAR(10) PRIMARY KEY
);
```

```sql
-- Composite PK (External)
CREATE TABLE Enrollment (
    OfferNumber INT,
    StdNo CHAR(11),

    CONSTRAINT pk_enrollment PRIMARY KEY (OfferNumber, StdNo)
);
```

---

## **Foreign Key Constraints**
A **foreign key (FK)** enforces referential integrity between tables.

### **Examples**
```sql
-- Foreign Key (Inline)
CREATE TABLE Enrollment (
    EnrollmentID INT PRIMARY KEY,
    StdNo CHAR(11) REFERENCES Students(StdNo)
);
```

```sql
-- Foreign Key (External)
CREATE TABLE Enrollment (
    EnrollmentID INT PRIMARY KEY,
    StdNo CHAR(11),
    
    CONSTRAINT fk_student FOREIGN KEY (StdNo) REFERENCES Students(StdNo)
        ON DELETE CASCADE ON UPDATE CASCADE
);
```
- **`ON DELETE CASCADE`** → Deletes child records if parent is deleted.
- **`ON UPDATE CASCADE`** → Updates child records when parent key changes.

---

## **Unique Constraints**
- Used for **candidate keys** (alternative unique identifiers).

```sql
CREATE TABLE Students (
    StdNo CHAR(11) PRIMARY KEY,
    Email VARCHAR(100) UNIQUE  -- Ensures no duplicate emails
);
```

---

## **Check Constraints**
- Ensures **values fall within valid ranges**.

#### **Examples**
```sql
-- GPA must be between 0.0 and 4.0
CONSTRAINT chk_gpa CHECK (GPA BETWEEN 0.0 AND 4.0);

-- Semester must be 'Fall', 'Spring', or 'Summer'
CONSTRAINT chk_semester CHECK (Semester IN ('Fall', 'Spring', 'Summer'));

-- A condition involving two columns
CONSTRAINT chk_dates CHECK (StartDate < EndDate);
```
- **Note**: `CHECK` constraints **cannot** reference another table.

---

## **Best Practices for Constraints**
1. **Always use meaningful names** for constraints (`pk_students`, `fk_enrollment_student`).
2. **Place NOT NULL constraints inline** for readability.
3. **Use external constraints** for multi-column rules.
4. **Be mindful of foreign key actions** (`CASCADE`, `SET NULL`, `RESTRICT`).
5. **Use CHECK constraints wisely** (they **cannot** reference other tables).

---

## **Conclusion**
- Constraints ensure **data integrity** in relational databases.
- Use **inline** constraints for **single-column rules**.
- Use **external** constraints for **composite keys and foreign keys**.
- Well-named constraints help in **debugging and maintenance**.
