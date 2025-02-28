# Basics of Relational Databases

## Why Are Relational Databases Commercially Dominant?

Relational databases dominate the industry due to their **familiarity and simplicity**.  
They were developed based on concepts that are intuitive to users:

- **Tables** are a natural way to represent data across many fields.
- **Rows and columns** are commonly used in spreadsheets, making them easy to understand.
- **Structured Query Language (SQL)** allows efficient data manipulation.

## Relational Database Basics

A relational database consists of **multiple tables** that store related information.

### Structure of a Table
Each table has:
- **Heading**  
  - Contains the table name and column names.
- **Body**  
  - Contains **rows**, where each row represents an **occurrence of data**.

### Example: University Database
A university database may have multiple related tables. For example:

#### **Students Table**
| Student_ID | Name      | Major    |
|------------|----------|----------|
| 1001       | Alice    | CS       |
| 1002       | Bob      | Math     |
| 1003       | Charlie  | Physics  |

#### **Enrollment Table**
| Enrollment_ID | Student_ID | Course_Code |
|--------------|------------|-------------|
| 1            | 1001       | CS101       |
| 2            | 1001       | CS102       |
| 3            | 1002       | MATH201     |

- **The `Student_ID` column in both tables serves as a key to establish a relationship.**  
- A student can enroll in multiple courses, so their `Student_ID` appears multiple times in the `Enrollment` table.

---

## Why Do We Need Multiple Tables?
A database contains **many tables**, each storing specific information.  
To retrieve meaningful insights, we often need to **combine tables using matching values**.

💡 **Next Lesson:**  
We will explore how to combine tables using **`JOIN`**, a crucial concept in relational databases.

---

## Understanding Table Connections

Understanding how tables are connected is essential for extracting useful information.  
For example, **joining the Students and Enrollment tables** helps us find:
- Which students are enrolled in a specific course.
- The list of courses a student has taken.

---

## Terminology in Relational Databases

Different terms are used depending on the context:

| **Table-Oriented** | **Set-Oriented** | **Record-Oriented** |
|--------------------|-----------------|---------------------|
| **Table**         | Relation        | Record Type, File  |
| **Row**           | Tuple           | Record             |
| **Column**        | Attribute       | Field              |

These terms are often mixed in professional settings, so it's useful to be familiar with all of them.

---

### Summary
- **Relational databases use tables** to store structured data.
- **Tables have rows (records) and columns (attributes).**
- **Combining tables using shared keys** is essential for retrieving meaningful data.
- **Different terminology exists**, but they refer to the same fundamental concepts.

---
