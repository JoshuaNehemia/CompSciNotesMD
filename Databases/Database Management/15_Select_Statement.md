# Select Statement

### Table of Contents

- [Select Statement](#select-statement)
    - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Questions to Consider](#questions-to-consider)
  - [The Importance of Query Formulation](#the-importance-of-query-formulation)
  - [Understanding the SELECT Statement](#understanding-the-select-statement)
    - [Basic Structure](#basic-structure)
    - [Column Expressions](#column-expressions)
    - [The FROM Clause](#the-from-clause)
    - [The WHERE Clause](#the-where-clause)
    - [Logical Expressions in WHERE Clause](#logical-expressions-in-where-clause)
    - [The ORDER BY Clause](#the-order-by-clause)
  - [Key Data Types in SQL](#key-data-types-in-sql)
  - [Example Queries](#example-queries)
    - [Example 1: Selecting All Columns and Rows](#example-1-selecting-all-columns-and-rows)
    - [Example 2: Filtering Rows with WHERE Clause](#example-2-filtering-rows-with-where-clause)
    - [Example 3: Selecting Specific Columns with Conditions](#example-3-selecting-specific-columns-with-conditions)
    - [Example 4: Removing Duplicate Rows with DISTINCT](#example-4-removing-duplicate-rows-with-distinct)
    - [Example 5: Using Expressions and Aliases](#example-5-using-expressions-and-aliases)
    - [Example 6: Pattern Matching with LIKE Operator](#example-6-pattern-matching-with-like-operator)
    - [Example 7: Date Range Matching](#example-7-date-range-matching)
    - [Example 8: Testing for NULL Values](#example-8-testing-for-null-values)
    - [Example 9: Logical Expressions with AND, OR, and Parentheses](#example-9-logical-expressions-with-and-or-and-parentheses)
  - [Best Practices in Query Formulation](#best-practices-in-query-formulation)
  - [Conclusion](#conclusion)
  - [Additional Resources](#additional-resources)

---

## Introduction

Welcome to **Lesson 2 of Module 4** on **basic query formulation with SQL**. In this lesson, you'll gain your first in-depth look at the `SELECT` statement, the foundation of data retrieval in SQL. Mastering this statement is crucial for anyone involved in application development or database management.

---

## Questions to Consider

Before diving in, reflect on these two pivotal questions:

1. **What database details should you know before you try to formulate a query?**
2. **When should you use parentheses when writing conditions to limit rows returned in the result?**

Understanding these will enhance your ability to write precise and efficient queries.

---

## The Importance of Query Formulation

**Query formulation** is an essential skill in application development. Regardless of your role—be it a developer or a database specialist—you'll need to interact with databases and retrieve data efficiently. Proficiency in SQL empowers you to extract meaningful insights, optimize application performance, and contribute significantly to your team's success.

---

## Understanding the SELECT Statement

The `SELECT` statement is the cornerstone of SQL query formulation. It allows you to specify exactly what data you want from the database and how you want it presented.

### Basic Structure

A basic `SELECT` statement follows this structure:

```sql
SELECT column_expressions
FROM tables
WHERE conditions
ORDER BY columns;
```

- **SELECT**: Lists the columns or expressions to return.
- **FROM**: Specifies the table(s) to query.
- **WHERE**: (Optional) Filters rows based on conditions.
- **ORDER BY**: (Optional) Sorts the result set.

### Column Expressions

In the `SELECT` clause, you can include not just column names but also **column expressions**:

- Arithmetic operations (e.g., `Salary * 1.1` to increase salary by 10%).
- Functions (e.g., `ROUND(Price, 2)`).
- Concatenations (e.g., `FirstName || ' ' || LastName`).

**Example**:

```sql
SELECT FacSalary * 1.1 AS IncreasedSalary
FROM Faculty;
```

- **IncreasedSalary** is an alias for the calculated column.

### The FROM Clause

Specifies the table(s) from which to retrieve data. In this lesson, we'll focus on queries involving a **single table**.

**Example**:

```sql
FROM Faculty
```

### The WHERE Clause

Filters the result set to include only rows that meet specified conditions.

**Example**:

```sql
WHERE FacRank = 'FULL' AND FacSalary > 65000;
```

### Logical Expressions in WHERE Clause

You can combine conditions using logical operators:

- **AND**: All conditions must be true.
- **OR**: At least one condition must be true.
- **NOT**: Reverses the truth value of a condition.

**Example**:

```sql
WHERE (OffTerm = 'FALL' AND OffYear = 2019) OR (OffTerm = 'WINTER' AND OffYear = 2020);
```

- Parentheses clarify the grouping of conditions.

### The ORDER BY Clause

Sorts the result set based on one or more columns, either in ascending (`ASC`) or descending (`DESC`) order.

**Example**:

```sql
ORDER BY FacLastName ASC, FacFirstName ASC;
```

---

## Key Data Types in SQL

Understanding data types is crucial for writing accurate queries. Focus on these three major types:

1. **Numeric**:
   - `INTEGER`, `DECIMAL`, `FLOAT`
   - Used for mathematical operations.
2. **Text**:
   - `CHAR`, `VARCHAR`
   - Stores strings of characters.
3. **Date/Time**:
   - `DATE`, `TIMESTAMP`
   - Represents dates and times.

**Important**: Always use constants and expressions compatible with the data type of the column.

---

## Example Queries

Let's explore practical examples to illustrate the concepts.

### Example 1: Selecting All Columns and Rows

```sql
SELECT *
FROM Faculty;
```

- **Explanation**: The `*` selects all columns. Without a `WHERE` clause, all rows are returned.

### Example 2: Filtering Rows with WHERE Clause

```sql
SELECT *
FROM Faculty
WHERE FacNo = 'F101';
```

- **Explanation**: Retrieves all data for the faculty member with `FacNo` equal to `'F101'`.

### Example 3: Selecting Specific Columns with Conditions

```sql
SELECT FacFirstName, FacLastName, FacSalary
FROM Faculty
WHERE FacRank = 'FULL' AND FacSalary > 65000;
```

- **Explanation**:
  - Selects only specified columns.
  - Filters for full professors earning over $65,000.
- **Note**: SQL is case-sensitive by default. Ensure that text constants match the case used in the database.

### Example 4: Removing Duplicate Rows with DISTINCT

```sql
SELECT DISTINCT FacCity, FacState
FROM Faculty;
```

- **Explanation**: Retrieves unique combinations of `FacCity` and `FacState`.
- **Use Case**: Identify all cities and states where faculty reside without duplicates.

### Example 5: Using Expressions and Aliases

```sql
SELECT FacFirstName, FacLastName, FacSalary * 1.1 AS IncreasedSalary
FROM Faculty
WHERE EXTRACT(YEAR FROM FacHireDate) > 2008;
```

- **Explanation**:
  - Calculates a 10% salary increase.
  - Uses `AS IncreasedSalary` to name the calculated column.
  - Filters for faculty hired after 2008 using `EXTRACT(YEAR FROM FacHireDate)`.
- **DBMS Differences**:
  - **Oracle** might use `TO_CHAR` and `TO_NUMBER` functions.
  - **PostgreSQL** uses `EXTRACT()` or `DATE_PART()`.

### Example 6: Pattern Matching with LIKE Operator

```sql
SELECT CourseNo, CourseName
FROM Course
WHERE CourseNo LIKE 'IS%';
```

- **Explanation**:
  - The `%` wildcard matches any sequence of characters.
  - Retrieves courses with numbers starting with `'IS'`.

### Example 7: Date Range Matching

```sql
SELECT FacFirstName, FacLastName, FacHireDate
FROM Faculty
WHERE FacHireDate BETWEEN '01-JAN-2010' AND '31-DEC-2020';
```

- **Explanation**:
  - Fetches faculty hired between specified dates.
  - Date format and syntax may vary between DBMSs.

### Example 8: Testing for NULL Values

```sql
SELECT OfferingNo, CourseNo, OffTerm, OffYear
FROM Offering
WHERE FacNo IS NULL;
```

- **Explanation**: Finds offerings where no instructor is assigned (`FacNo` is `NULL`).
- **Important**: Use `IS NULL` or `IS NOT NULL` for testing `NULL` values.

### Example 9: Logical Expressions with AND, OR, and Parentheses

```sql
SELECT OfferingNo, CourseNo, OffTerm, OffYear
FROM Offering
WHERE (OffTerm = 'FALL' AND OffYear = 2019) OR (OffTerm = 'WINTER' AND OffYear = 2020);
```

- **Explanation**:
  - Retrieves offerings from Fall 2019 or Winter 2020.
  - Parentheses ensure correct logical grouping.
- **Best Practice**: Always use parentheses when mixing `AND` and `OR`.

---

## Best Practices in Query Formulation

- **Understand the Database Schema**:
  - Use database diagrams to know table structures and relationships.
  - Essential for accurate query formulation.

- **Use Compatible Data Types**:
  - Match constants and expressions to the column data types.
  - Avoid mixing data types in comparisons (e.g., don't compare a numeric column to a text string).

- **Be Mindful of Case Sensitivity**:
  - SQL is case-sensitive for string comparisons by default.
  - Ensure that text constants match the case used in the database.

- **Parentheses in Logical Expressions**:
  - Clarify the grouping of conditions.
  - Avoids ambiguity and ensures the query behaves as intended.
  - Enhances readability for others reviewing your code.

- **Testing and Execution**:
  - Practice writing and executing queries in both Oracle SQL Developer and PostgreSQL's pgAdmin.
  - Helps understand differences and improve query portability.

- **Handling NULL Values**:
  - Recognize that `NULL` represents unknown or missing data.
  - Use `IS NULL` and `IS NOT NULL` for accurate testing.

- **Avoid Non-Portable Functions**:
  - Be cautious with DBMS-specific functions (like date functions).
  - Aim for standard SQL functions when possible to enhance portability.

---

## Conclusion

In this lesson, you've gained foundational knowledge of the SQL `SELECT` statement and how to formulate basic queries involving single tables. You've learned how to:

- **Select specific data** using column expressions and aliases.
- **Filter results** with the `WHERE` clause and logical expressions.
- **Handle different data types** appropriately in queries.
- **Perform pattern matching** with the `LIKE` operator and wildcards.
- **Test for NULL values**, ensuring data integrity.
- **Use parentheses** to structure complex logical conditions.

These skills are essential stepping stones toward more advanced SQL concepts, such as joining multiple tables and performing aggregations.

---

## Additional Resources

- **SQL Documentation**:
  - [Oracle SQL Documentation](https://docs.oracle.com/en/database/)
  - [PostgreSQL Documentation](https://www.postgresql.org/docs/)

- **Online SQL Editors**:
  - [Oracle Live SQL](https://livesql.oracle.com/)
  - [DB Fiddle for PostgreSQL](https://www.db-fiddle.com/)

- **Tutorials and Guides**:
  - [W3Schools SQL Tutorial](https://www.w3schools.com/sql/)
  - [SQL Tutorial by TutorialsPoint](https://www.tutorialspoint.com/sql/index.htm)

- **Practice Exercises**:
  - Create queries to answer specific questions using the sample database.
  - Modify the example queries to retrieve different data sets.
