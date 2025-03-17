# SQL Modification Statements – INSERT, UPDATE, and DELETE

---

## Opening Question: Why Are Modification Statements (INSERT, UPDATE, DELETE) Less Widely Used Than the SELECT Statement?

The **modification statements**—**INSERT**, **UPDATE**, and **DELETE**—allow changes to the database by adding, updating, or deleting rows. However, they are less widely used directly by end users compared to the **SELECT** statement because:

1. **Indirect Usage in Applications**:
   - Most users interact with databases through **custom data entry forms**, not by writing SQL modification statements.
   - These forms use **auto-generated SQL** (from code generators) or SQL embedded in host programs, sparing users from manual entry.

2. **Prevalence of Data Retrieval**:
   - The **SELECT** statement is used for querying data, which is more frequent in analysis, reporting, and decision-making than modifying data.

3. **Potential Complexity**:
   - Changing data (e.g., modifying primary keys or adhering to referential constraints) can introduce complexities that end users might not be equipped to handle.

4. **Risk Management**:
   - Direct modification requires careful handling to avoid unintentional data loss or corruption. It’s often restricted to experienced users or automated systems.

---

## Lesson Objectives

1. Understand the purpose of **INSERT**, **UPDATE**, and **DELETE**.
2. Write basic examples of each statement, focusing on single-table operations.
3. Recognize the specialized roles of these modification statements in data integration.

---

## Overview of SQL Modification Statements

| **Statement** | **Purpose**                                     |
|---------------|-------------------------------------------------|
| **INSERT**    | Add new rows to a table.                       |
| **UPDATE**    | Modify column values in one or more rows.       |
| **DELETE**    | Remove one or more rows from a table.           |

---

## 1. INSERT Statement

The **INSERT** statement adds new rows to a table. Two formats exist:
- **Single-Row Insertion**: Covered in this course.
- **Multiple-Row Insertion**: Covered in future courses (e.g., Course 3).

### Syntax: Single-Row Insertion

```sql
INSERT INTO table_name (column1, column2, ...)
VALUES (value1, value2, ...);
```

### Example

```sql
INSERT INTO Student (StdNo, StdFirstName, StdLastName, StdGPA)
VALUES (101, 'John', 'Doe', 3.8);
```

- **Columns and Values**:
  - Match specified columns to corresponding values.
  - Use data types compatible with column definitions.

### Notes

- **NULL Values**: Ensure the table allows NULL values for columns omitted in the `INSERT` statement.
- **Referential Integrity**:
  - Parent keys in a foreign key relationship must exist before inserting child rows.

---

## 2. UPDATE Statement

The **UPDATE** statement modifies data in one or more rows. Changes may involve multiple columns, but typically, only one column is updated at a time.

### Syntax

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

- **WHERE Clause**:
  - Specifies rows to update.
  - Omitting it will update **all rows** in the table (use cautiously).

### Example

```sql
UPDATE Student
SET StdGPA = 3.9
WHERE StdNo = 101;
```

- **Primary Key Changes**:
  - Avoid changing primary key values to prevent disrupting referential integrity.
  - Parent table primary key changes may require updates to related child rows.

---

## 3. DELETE Statement

The **DELETE** statement removes rows from a table.

### Syntax

```sql
DELETE FROM table_name
WHERE condition;
```

- **WHERE Clause**:
  - Restricts rows to be deleted.
  - Omitting it will delete **all rows** in the table (equivalent to truncating the table).

### Example

```sql
DELETE FROM Student
WHERE StdNo = 101;
```

- **Referential Constraints**:
  - Ensure child rows (if any) in related tables are handled according to the **ON DELETE** actions (`RESTRICT`, `CASCADE`, etc.).

---

## Practical Considerations

1. **Generated SQL Statements**:
   - Modification statements are typically written by **programmers** or **code generators** and embedded into applications for tasks like data entry or batch processing.

2. **Custom Data Entry Forms**:
   - Most users interact with these statements indirectly through GUIs.

3. **Referential Integrity**:
   - Modifications must comply with database constraints to ensure data consistency.

4. **Risks of Manual Usage**:
   - Direct use can lead to data loss or corruption if not carefully managed.

---

## Key Takeaways

- **INSERT**, **UPDATE**, and **DELETE**:
  - Allow adding, modifying, and removing rows in a database.
  - Are less frequently used directly by users compared to **SELECT** statements.
  
- **Real-World Application**:
  - Typically executed indirectly via applications or automated tools.

- **Referential Integrity**:
  - Always consider database constraints, such as primary and foreign key relationships, when using modification statements.

