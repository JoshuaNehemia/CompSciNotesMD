# Combining Joins and Grouping in SQL for Business Intelligence

## Opening Motivation: Why Are Joins and Grouping a Powerful Combination?

Joins and grouping are essential tools for **business intelligence processing**. Their combination allows:

1. **Data Integration**:
   - Joins enable combining data from multiple related tables, creating a unified dataset for analysis.
2. **Summarization**:
   - Grouping condenses large datasets into meaningful summaries using aggregate functions like `SUM`, `COUNT`, `AVG`, etc.
3. **Advanced Analysis**:
   - Together, they help answer complex questions, such as analyzing trends, summarizing data by categories, and generating insights essential for decision-making.
4. **Optimized Data Structures**:
   - Data warehouses often design table structures that rely heavily on joins and grouping for efficient querying.

---

## Lesson Objectives

1. **Analyze Complex Problem Statements**:
   - Use the **critical questions** to break down problems with **multiple joins** and **grouping requirements**.
2. **Apply Extended Statement Patterns**:
   - Write `SELECT` statements with **multiple joins**, **grouping clauses**, and **aggregate functions**.

---

## Grouping Statement Patterns for Joins

### Extended Cross-Product Join Style
- **FROM Clause**: Lists N tables.
- **WHERE Clause**:
  - Includes **N - 1 join conditions** to connect tables.
  - Additional row conditions if needed.
- **SELECT Clause**:
  - Contains a mix of **aggregate functions** (e.g., `COUNT`, `AVG`) and columns without aggregation.
- **GROUP BY Clause**:
  - Lists every column used in the `SELECT` clause, except for those in aggregate functions.
- **HAVING Clause**:
  - Contains conditions involving **aggregate functions**.

### Extended Join Operator Style
- Similar to the cross-product style, but uses explicit `JOIN` and `ON` syntax for clarity.

---

## Examples Using Critical Questions

### Example 1: Count of Students and Average GPA

#### Problem Statement
Determine the **count of students enrolled** and **average GPA** for each offering in a specific year.

#### Critical Questions

1. **What Tables?**
   - **Enrollment**: For counting students.
   - **Offering**: To filter by offering year.
   - **Student**: To calculate the average GPA.

2. **How Are Tables Combined?**
   - **Enrollment** ↔ **Offering**: Joined on `OfferNo`.
   - **Enrollment** ↔ **Student**: Joined on `StdNo`.

3. **Individual Rows or Groups of Rows?**
   - **Groups of Rows**:
     - `COUNT` for the number of students.
     - `AVG` for GPA.

#### SQL Query (Cross-Product Style)

```sql
SELECT Offering.OfferNo, 
       COUNT(*) AS StudentCount, 
       AVG(Student.StdGPA) AS AvgGPA
FROM Enrollment, Offering, Student
WHERE Enrollment.OfferNo = Offering.OfferNo
  AND Enrollment.StdNo = Student.StdNo
  AND Offering.OfferYear = 2022
GROUP BY Offering.OfferNo
HAVING AVG(Student.StdGPA) > 3.0;
```

---

### Example 2: Students Enrolled by Offering and Course

#### Problem Statement
Show the **count of students** for each offering by **offer number** and **course number** in a specific term and year.

#### Critical Questions

1. **What Tables?**
   - **Offering**: Provides `OfferNo` and `CourseNo`.
   - **Enrollment**: Used to calculate student count.

2. **How Are Tables Combined?**
   - **Enrollment** ↔ **Offering**: Joined on `OfferNo`.

3. **Individual Rows or Groups of Rows?**
   - **Groups of Rows**:
     - Grouped by `OfferNo` and `CourseNo`.

#### SQL Query (Cross-Product Style)

```sql
SELECT Offering.OfferNo, 
       Offering.CourseNo, 
       COUNT(*) AS StudentCount
FROM Enrollment, Offering
WHERE Enrollment.OfferNo = Offering.OfferNo
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2022
GROUP BY Offering.OfferNo, Offering.CourseNo;
```

---

### Example 3: Average GPA and Faculty Names

#### Problem Statement
Find the **average GPA of students**, grouped by faculty member and offering, for a specific term and year.

#### Critical Questions

1. **What Tables?**
   - **Offering**: For filtering by term and year.
   - **Student**: For calculating average GPA.
   - **Faculty**: To include faculty names.
   - **Enrollment**: Connects the tables.

2. **How Are Tables Combined?**
   - **Faculty** ↔ **Offering**: Joined on `FacNo`.
   - **Offering** ↔ **Enrollment**: Joined on `OfferNo`.
   - **Enrollment** ↔ **Student**: Joined on `StdNo`.

3. **Individual Rows or Groups of Rows?**
   - **Groups of Rows**:
     - Grouped by `FacFirstName`, `FacLastName`, `OfferNo`.

#### SQL Query (Cross-Product Style)

```sql
SELECT Offering.OfferNo, 
       Faculty.FacFirstName, 
       Faculty.FacLastName, 
       AVG(Student.StdGPA) AS AvgGPA
FROM Enrollment, Offering, Student, Faculty
WHERE Enrollment.OfferNo = Offering.OfferNo
  AND Enrollment.StdNo = Student.StdNo
  AND Offering.FacNo = Faculty.FacNo
  AND Offering.OffTerm = 'FALL'
  AND Offering.OffYear = 2022
GROUP BY Offering.OfferNo, Faculty.FacFirstName, Faculty.FacLastName
HAVING AVG(Student.StdGPA) > 3.0;
```

---

## Key Takeaways

- **Joins**: Enable data integration by combining related tables.
- **Grouping**: Summarizes data for meaningful insights.
- **Combining Joins and Grouping**:
  - Particularly valuable for business intelligence tasks.
  - Supports complex queries, such as summarizing enrollment data, calculating averages, and segmenting results.

Joins and grouping are the backbone of SQL-based analytical queries, essential for transforming raw data into actionable insights. These techniques are foundational for crafting efficient, scalable, and impactful business intelligence solutions.