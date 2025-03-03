# Using the GROUP BY and HAVING Clauses for Row Summaries

---

### Table of Contents

- [Using the GROUP BY and HAVING Clauses for Row Summaries](#using-the-group-by-and-having-clauses-for-row-summaries)
    - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Objectives](#objectives)
  - [The Need for Row Summaries](#the-need-for-row-summaries)
  - [Aggregate Functions in SQL](#aggregate-functions-in-sql)
  - [Understanding the `GROUP BY` Clause](#understanding-the-group-by-clause)
  - [Using the `HAVING` Clause for Group Conditions](#using-the-having-clause-for-group-conditions)
  - [Comparison of `WHERE` and `HAVING` Clauses](#comparison-of-where-and-having-clauses)
  - [Evaluation Order in `SELECT` Statements](#evaluation-order-in-select-statements)
  - [Examples](#examples)
    - [Example 1: Listing Individual Salaries](#example-1-listing-individual-salaries)
    - [Example 2: Average Salary by Rank](#example-2-average-salary-by-rank)
    - [Example 3: Average GPA for Juniors and Seniors](#example-3-average-gpa-for-juniors-and-seniors)
    - [Example 4: Filtering Groups with `HAVING`](#example-4-filtering-groups-with-having)
    - [Example 5: Common Mistake with `HAVING` Clause](#example-5-common-mistake-with-having-clause)
    - [Example 6: Common Mistake with `WHERE` Clause](#example-6-common-mistake-with-where-clause)
  - [Limitations of the `GROUP BY` Clause in Business Intelligence](#limitations-of-the-group-by-clause-in-business-intelligence)
  - [Conclusion](#conclusion)
  - [Additional Resources](#additional-resources)

---

## Introduction

Welcome to **Lesson 5 of Module 4** on **basic query formulation with SQL**. In this lesson, we will explore two new clauses of the `SELECT` statement that enable us to summarize data:

- The `GROUP BY` clause
- The `HAVING` clause

These clauses allow us to generate **row summaries** and perform rudimentary reporting, which is essential for data analysis and business intelligence.

---

## Objectives

By the end of this lesson, you should be able to:

- Understand and use the `GROUP BY` clause to create row summaries.
- Apply aggregate functions like `COUNT`, `SUM`, `AVG`, `MIN`, and `MAX`.
- Use the `HAVING` clause to filter groups based on aggregate values.
- Differentiate between `WHERE` and `HAVING` clauses.
- Recognize the limitations of the `GROUP BY` clause for business intelligence queries.

---

## The Need for Row Summaries

In databases with extensive data, it's often insufficient to examine individual rows. Instead, summarizing data provides valuable insights:

- **Statistical Analysis**: Calculate averages, totals, counts, etc.
- **Group Insights**: Understand patterns within subsets of data.
- **Decision-Making**: Inform strategic and tactical business decisions.

**Example**: Determining the **average GPA** of students in each major helps identify which departments might need academic support or resources.

---

## Aggregate Functions in SQL

SQL provides several aggregate functions to perform calculations on sets (groups) of rows:

| Function | Description                      |
|----------|----------------------------------|
| `COUNT`  | Counts the number of rows        |
| `SUM`    | Calculates the sum of values     |
| `AVG`    | Calculates the average value     |
| `MIN`    | Finds the minimum value          |
| `MAX`    | Finds the maximum value          |

**Usage Example**:

```sql
SELECT AVG(FacSalary)
FROM Faculty;
```

---

## Understanding the `GROUP BY` Clause

The `GROUP BY` clause groups rows that have the same values in specified columns into summary rows. It is often used with aggregate functions.

**Syntax**:

```sql
SELECT column1, AGG_FUNC(column2)
FROM table_name
GROUP BY column1;
```

- **`column1`**: The column to group by.
- **`AGG_FUNC`**: Aggregate function applied to each group.

**Example**:

```sql
SELECT FacRank, AVG(FacSalary) AS AvgSalary
FROM Faculty
GROUP BY FacRank;
```

- Groups faculty by `FacRank`.
- Calculates the average salary for each rank.

---

## Using the `HAVING` Clause for Group Conditions

The `HAVING` clause filters groups based on aggregate function results, similar to how the `WHERE` clause filters rows.

**Syntax**:

```sql
SELECT column1, AGG_FUNC(column2)
FROM table_name
GROUP BY column1
HAVING AGG_FUNC(column2) condition value;
```

**Example**:

```sql
SELECT Major, AVG(StudGPA) AS AvgGPA
FROM Student
GROUP BY Major
HAVING AVG(StudGPA) > 3.1;
```

- Only includes majors where the average GPA is greater than 3.1.

---

## Comparison of `WHERE` and `HAVING` Clauses

- **`WHERE` Clause**:
  - Filters individual rows **before** grouping.
  - Cannot use aggregate functions.

- **`HAVING` Clause**:
  - Filters groups **after** aggregation.
  - Can use aggregate functions.

**Key Differences**:

- Use `WHERE` for conditions on individual rows.
- Use `HAVING` for conditions on aggregated data.

---

## Evaluation Order in `SELECT` Statements

Understanding the evaluation order helps in writing correct queries:

1. **FROM**: Tables are selected and joins are performed.
2. **WHERE**: Filters individual rows.
3. **GROUP BY**: Rows are grouped.
4. **HAVING**: Filters groups.
5. **SELECT**: Columns and expressions are computed.
6. **ORDER BY**: Results are sorted.

---

## Examples

Let's delve into practical examples to illustrate these concepts.

### Example 1: Listing Individual Salaries

**Objective**: List the salary of each faculty member, sorted by rank.

```sql
SELECT FacRank, FacFirstName, FacLastName, FacSalary
FROM Faculty
ORDER BY FacRank, FacSalary DESC;
```

**Result**:

| FacRank   | FacFirstName | FacLastName | FacSalary |
|-----------|--------------|-------------|-----------|
| ASSISTANT | Alice        | Smith       | 60,000    |
| ASSISTANT | Bob          | Johnson     | 62,000    |
| ASSOCIATE | Carol        | Williams    | 70,000    |
| ASSOCIATE | David        | Jones       | 75,000    |
| FULL      | Eve          | Brown       | 80,000    |
| FULL      | Frank        | Davis       | 85,000    |

### Example 2: Average Salary by Rank

**Objective**: Show the average salary for each faculty rank.

```sql
SELECT FacRank, AVG(FacSalary) AS AvgSalary
FROM Faculty
GROUP BY FacRank;
```

**Result**:

| FacRank   | AvgSalary |
|-----------|-----------|
| ASSISTANT | 61,000    |
| ASSOCIATE | 72,500    |
| FULL      | 82,500    |

- **Explanation**:
  - **ASSISTANT**: Average of 60,000 and 62,000.
  - **ASSOCIATE**: Average of 70,000 and 75,000.
  - **FULL**: Average of 80,000 and 85,000.

### Example 3: Average GPA for Juniors and Seniors

**Objective**: Calculate the average GPA for each major, considering only juniors and seniors.

```sql
SELECT Major, AVG(StudGPA) AS AvgGPA
FROM Student
WHERE StClass IN ('JUNIOR', 'SENIOR')
GROUP BY Major;
```

- **Note**: `StClass` represents the student's class level.

### Example 4: Filtering Groups with `HAVING`

**Objective**: Extend Example 3 to include only majors with an average GPA greater than 3.1.

```sql
SELECT Major, AVG(StudGPA) AS AvgGPA
FROM Student
WHERE StClass IN ('JUNIOR', 'SENIOR')
GROUP BY Major
HAVING AVG(StudGPA) > 3.1;
```

- **Explanation**:
  - Filters out majors where the average GPA is 3.1 or less.

### Example 5: Common Mistake with `HAVING` Clause

**Objective**: Incorrectly placing a row condition in the `HAVING` clause.

```sql
SELECT Major, AVG(StudGPA) AS AvgGPA
FROM Student
GROUP BY Major
HAVING StClass IN ('JUNIOR', 'SENIOR');
```

- **Error**:
  - **Problem**: `StClass` is an individual row attribute, not an aggregate.
  - **Result**: SQL compiler raises an error.

### Example 6: Common Mistake with `WHERE` Clause

**Objective**: Incorrectly placing a group condition in the `WHERE` clause.

```sql
SELECT Major, AVG(StudGPA) AS AvgGPA
FROM Student
WHERE AVG(StudGPA) > 3.1
GROUP BY Major;
```

- **Error**:
  - **Problem**: Cannot use aggregate functions in the `WHERE` clause.
  - **Result**: SQL compiler raises an error.

---

## Limitations of the `GROUP BY` Clause in Business Intelligence

While the `GROUP BY` clause is powerful, it has limitations when dealing with complex business intelligence queries:

- **Single Level Grouping**: Cannot naturally produce multiple levels of subtotals and grand totals.
- **Advanced Analytics**: Lacks support for ranking, moving averages, and cumulative distributions.
- **Complex Calculations**: Not suited for window functions or analytical functions required in sophisticated analyses.

**Solution**:

- Use **Online Analytical Processing (OLAP)** extensions or **window functions** (e.g., `OVER` clause) available in advanced SQL versions.
- Employ specialized BI tools and languages that support complex data analysis.

---

## Conclusion

In this lesson, we've explored:

- The use of aggregate functions to summarize data.
- How the `GROUP BY` clause groups rows for aggregation.
- The role of the `HAVING` clause in filtering groups based on aggregate conditions.
- The evaluation order of SQL clauses and how it affects query results.
- Common mistakes when misplacing conditions in `WHERE` and `HAVING` clauses.
- Limitations of the `GROUP BY` clause for advanced business intelligence needs.

Understanding these concepts is essential for crafting effective SQL queries that provide meaningful insights from your data.

---

## Additional Resources

- **SQL Documentation**:
  - [Oracle SQL Language Reference](https://docs.oracle.com/en/database/)
  - [PostgreSQL Documentation](https://www.postgresql.org/docs/)
- **Tutorials**:
  - [W3Schools SQL Tutorial on GROUP BY](https://www.w3schools.com/sql/sql_groupby.asp)
  - [Mode Analytics SQL Tutorial](https://mode.com/sql-tutorial/sql-having-clause/)
- **Practice Exercises**:
  - Try writing queries using the `GROUP BY` and `HAVING` clauses on sample datasets.
  - Experiment with aggregate functions on different columns and conditions.

---

*Remember, mastering SQL requires consistent practice. Utilize small sample tables to test and understand your queries, especially when dealing with complex conditions and aggregates.*