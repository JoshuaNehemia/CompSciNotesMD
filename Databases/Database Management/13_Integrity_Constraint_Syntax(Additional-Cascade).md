### **Understanding `ON DELETE CASCADE` and `ON UPDATE CASCADE` in SQL**  

When defining **foreign keys (FKs)** in SQL, you can specify actions that should happen **when the referenced (parent) table is updated or deleted**. Two commonly used actions are:  

- **`ON DELETE CASCADE`** → If a record in the parent table is deleted, all related records in the child table are automatically deleted.
- **`ON UPDATE CASCADE`** → If the primary key (PK) of a record in the parent table is updated, all related records in the child table are automatically updated.

---

## **Example: Using `ON DELETE CASCADE` and `ON UPDATE CASCADE`**
Consider the following **`Students`** and **`Enrollment`** tables:

```sql
CREATE TABLE Students (
    StdNo CHAR(11) PRIMARY KEY,
    Name VARCHAR(50) NOT NULL
);

CREATE TABLE Enrollment (
    EnrollmentID INT PRIMARY KEY,
    StdNo CHAR(11),
    CourseCode VARCHAR(10) NOT NULL,

    -- Foreign Key Constraint with CASCADE
    CONSTRAINT fk_student FOREIGN KEY (StdNo) REFERENCES Students(StdNo) 
        ON DELETE CASCADE 
        ON UPDATE CASCADE
);
```

---

## **How It Works?**
### 🔴 **Scenario 1: `ON DELETE CASCADE`**
```sql
DELETE FROM Students WHERE StdNo = 'S1001';
```
- The student **`S1001`** is deleted from `Students`.
- **All `Enrollment` records related to `S1001` are also deleted**.

---

### 🔄 **Scenario 2: `ON UPDATE CASCADE`**
```sql
UPDATE Students SET StdNo = 'S2001' WHERE StdNo = 'S1001';
```
- The student ID **`S1001`** is updated to **`S2001`**.
- **All `Enrollment` records that referenced `S1001` are automatically updated to `S2001`**.

---

## **Other Cascade Options**
| Constraint | Behavior |
|------------|----------|
| `ON DELETE SET NULL` | Deletes the parent record, but sets the child record’s FK to `NULL`. |
| `ON UPDATE SET NULL` | Updates the parent PK, and sets the child FK to `NULL`. |
| `ON DELETE RESTRICT` | Prevents deletion of the parent record if child records exist. |
| `ON UPDATE RESTRICT` | Prevents updates to the parent PK if child records exist. |

---

## **Best Practices**
✅ Use **`CASCADE`** when **dependent data should be removed or updated** automatically.  
✅ Use **`RESTRICT`** if **you don’t want accidental deletions/updates**.  
✅ Use **`SET NULL`** when **child records can exist without the parent**.  

Would you like more examples or modifications for specific scenarios? 🚀