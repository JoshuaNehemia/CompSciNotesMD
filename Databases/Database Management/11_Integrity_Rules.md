# Integrity Rules in Relational Databases

## Introduction 

> **Critical Thinking!**  
> What happens if two taxpayers have the same ID number?  
> What if a single shipment order has two different ID numbers?  

To maintain **accuracy and consistency** in a relational database, **integrity rules** must be enforced.

---

## Key Definitions

### **Null Values**
- Represents the **absence of a value**.
- Can indicate that a value is **unknown or not applicable** for a row.

### **Primary Keys (PK)**
- A **column or combination of columns** with unique values in each row.
- Ensures that each record is **uniquely identifiable**.
- Should be **minimal**—no extra columns should be included.

### **Foreign Keys (FK)**
- A **column or combination of columns** in one table that **references** a primary key in another table.
- Maintains **relationships** between tables.
- Must have the **same data type** and often the same name as the related primary key.
- Ensures **referential integrity** (explained later).

---

## Example: University Database  

### **Students Table**  
Each student has a **unique Student_ID**.

| Student_ID | Name      | Major    |
|------------|----------|----------|
| 1001       | Alice    | CS       |
| 1002       | Bob      | Math     |
| 1003       | Charlie  | Physics  |

### **Enrollment Table**  
Each row represents a student's **course enrollment**.  
The `Student_ID` column here is a **foreign key** that references the `Student_ID` in the **Students Table**.

| Enrollment_ID | Student_ID | Course_Code |
|--------------|------------|-------------|
| 1            | 1001       | CS101       |
| 2            | 1001       | CS102       |
| 3            | 1002       | MATH201     |

💡 **Key Observations:**  
- **`Student_ID` is unique in the Students table** (Primary Key).  
- **`Student_ID` is repeated in the Enrollment table** to track multiple enrollments.  
- The relationship is **minimal**, meaning no extra columns are included.

---

## Integrity Rules

### **1. Entity Integrity**
> **Ensures every entity (record) is uniquely identifiable.**  

- Every table **must have a primary key**.
- The **primary key cannot contain NULL values**.
- Guarantees that each row is **traceable and unique**.

**Example:**  
If a `Student_ID` were NULL, we would **lose track of the student** in other related tables.

### **2. Referential Integrity**
> **Ensures valid relationships between tables.**  

- A **foreign key value** in one table must match a **primary key value** in another table.
- **Two valid values for a foreign key:**
  1. **A matching primary key value** from the referenced table (most common).
  2. **NULL value** (unusual, but possible if the relationship is optional).

**Example:**  
In the Enrollment table, every `Student_ID` **must exist in the Students table**.  
If a `Student_ID` references a non-existent student, it would create **orphaned records**.

---

## Summary  

- **Entity Integrity** ensures each table has a **unique and traceable** primary key.  
- **Referential Integrity** enforces **valid relationships** between tables using foreign keys.  
- These rules **prevent data inconsistency** and maintain database reliability.  

---