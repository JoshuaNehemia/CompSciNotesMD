# Lesson 6: SQL Query Formulation Errors

---

## Opening Questions
1. **What query formulation error can lead to a loss of a job?**
   - A **missing join condition** is the most critical error. On large tables, it can generate excessive rows and consume vast resources, potentially leading to poor work evaluations or even job loss.

2. **What is the most difficult error to detect?**
   - A **semantic error** that generates seemingly correct rows is the most challenging to identify. It might go unnoticed until additional data is added, causing incorrect results.

---

## Lesson Objectives
1. Learn to **avoid query formulation errors** by understanding their types and causes.
2. Acquire skills to **detect and correct errors** in your statements and those made by others.
3. Strive for **good coding practices** to make SQL statements readable and maintainable.

---

## Types of Query Formulation Errors

1. **Syntax Errors**:
   - **Definition**: Occur when SQL syntax rules are violated.
   - **Detection**: Easy to detect because the SQL compiler provides error messages.
   - **Example**:
     - Misspelled keyword: `SELCET` instead of `SELECT`.
     - Missing table name or unqualified column name.

2. **Redundancy Errors**:
   - **Definition**: Statements produce correct rows but consume extra resources unnecessarily.
   - **Examples**:
     - Including an extra table in the `FROM` clause.
     - Adding a `GROUP BY` clause when no summary calculations are needed.

3. **Semantic Errors**:
   - **Definition**: Statements produce incorrect results (e.g., too many or too few rows).
   - **Severity**: Most serious because they may not immediately appear incorrect.
   - **Examples**:
     - Missing join condition.
     - Incorrect logical grouping due to missing parentheses.

---

## Error Examples

### **Example 1: Missing Join Condition (Semantic Error)**

**Problem**: List student names and offering numbers where students earned a grade > 3.7 in Fall 2019.

**Faulty Query**:

```sql
SELECT StdName, OfferNo
FROM Student, Enrollment, Offering
WHERE Enrollment.Grade > 3.7
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2019;
```

**Error**: Missing join conditions between `Student`, `Enrollment`, and `Offering`. This generates excessive, unrelated rows.

**Correct Query**:

```sql
SELECT StdName, OfferNo
FROM Student
JOIN Enrollment ON Student.StdNo = Enrollment.StdNo
JOIN Offering ON Enrollment.OfferNo = Offering.OfferNo
WHERE Enrollment.Grade > 3.7
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2019;
```

---

### **Example 2: Redundant `GROUP BY` Clause (Redundancy Error)**

**Problem**: Same as Example 1.

**Faulty Query**:

```sql
SELECT StdName, OfferNo
FROM Student
JOIN Enrollment ON Student.StdNo = Enrollment.StdNo
JOIN Offering ON Enrollment.OfferNo = Offering.OfferNo
WHERE Enrollment.Grade > 3.7
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2019
GROUP BY StdName, OfferNo;
```

**Error**: The `GROUP BY` clause is unnecessary because no summary calculations are performed.

**Correct Query**:
(Omit the `GROUP BY` clause):
```sql
SELECT StdName, OfferNo
FROM Student
JOIN Enrollment ON Student.StdNo = Enrollment.StdNo
JOIN Offering ON Enrollment.OfferNo = Offering.OfferNo
WHERE Enrollment.Grade > 3.7
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2019;
```

---

### **Example 3: Missing Parentheses (Semantic Error)**

**Problem**: List offerings scheduled in Spring or Summer 2019.

**Faulty Query**:

```sql
SELECT OfferNo, CourseNo, FacNo
FROM Offering
WHERE OffTerm = 'SPRING'
  OR OffTerm = 'SUMMER'
  AND OffYear = 2019;
```

**Error**: Missing parentheses causes incorrect evaluation. Without parentheses, `AND` has higher precedence than `OR`. The query filters only `SUMMER` 2019 and combines it with `SPRING` rows from all years.

**Correct Query**:

1. Add Parentheses:
```sql
SELECT OfferNo, CourseNo, FacNo
FROM Offering
WHERE (OffTerm = 'SPRING' OR OffTerm = 'SUMMER')
  AND OffYear = 2019;
```

2. Use `IN` Operator:
```sql
SELECT OfferNo, CourseNo, FacNo
FROM Offering
WHERE OffTerm IN ('SPRING', 'SUMMER')
  AND OffYear = 2019;
```

---

## Good Coding Practices

Beyond avoiding errors, strive for **readable and maintainable code** by adopting these practices:

1. **Clause Alignment**:
   - Align `SELECT`, `FROM`, `WHERE`, `GROUP BY`, and `ORDER BY` clauses vertically.
2. **Meaningful Aliases**:
   - Use short but descriptive aliases for tables and columns.
3. **Avoid Incompatible Constants**:
   - Ensure constants match the column's data type.
4. **Pattern Matching**:
   - Use the `LIKE` operator only when a pattern-matching character (e.g., `%` or `_`) is necessary.

---

### **Example 4: Poor Coding Practices**

**Faulty Query**:
```sql
SELECT * FROM Student
WHERE StdFirstName LIKE 'John'
AND OffYear = "2020";
```

**Errors**:
1. **Poor Clause Alignment**: The query is difficult to read.
2. **Incompatible Constants**: `OffYear = "2020"` uses double quotes instead of single quotes.
3. **Incorrect `LIKE` Usage**: The `LIKE` operator is used without a wildcard.

**Improved Query**:
```sql
SELECT *
FROM Student
WHERE StdFirstName = 'John'
  AND OffYear = '2020';
```

---

## Key Takeaways

1. **Error Types**:
   - Syntax Errors: Detectable by SQL compilers but sometimes hard to fix.
   - Redundancy Errors: Produce correct results but waste resources.
   - Semantic Errors: Generate incorrect results, often with severe consequences.

2. **Most Severe Error**:
   - A **missing join condition** can cause excessive rows, leading to poor performance evaluations or job loss.

3. **Most Subtle Error**:
   - A **semantic error** that seems correct under limited conditions but fails with new data.

4. **Good Practices**:
   - Write clean, well-aligned code.
   - Avoid unnecessary clauses.
   - Use proper constants and operators.

By understanding and avoiding common errors, you can streamline query formulation, improve collaboration, and gain confidence in your SQL skills. 
