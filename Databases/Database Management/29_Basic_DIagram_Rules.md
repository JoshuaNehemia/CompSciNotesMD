# ERD Rules and Problem Solving

---

## Opening Question: What Kind of Errors with Primary Keys Cannot Be Detected by the Diagram Rules?

Diagram rules for primary keys ensure that every entity type has a primary key, but they **cannot guarantee** that:
1. **The Chosen Primary Key is Appropriate**:
   - A primary key might fulfill diagram rules but fail to meet real-world business needs.
   - Example: Using a government identifier (e.g., Social Security Number) may seem correct but is unreliable due to issues like fraud or duplicate assignments.

2. **Business Requirements are Met**:
   - Diagram rules do not validate whether the chosen primary key aligns with the database’s semantic requirements.

### Conclusion:
Diagram rules focus on **notation correctness** but do not address **design quality or appropriateness**. Selecting an effective primary key requires an understanding of the business context, covered in Modules 8 and 9.

---

## Lesson Objectives

1. Apply **completeness rules** to ensure no critical omissions in ERDs, such as missing primary keys or cardinalities.
2. Reflect on the **limitations** of diagram rules.
3. Develop a habit of checking ERDs for **consistency** and **notation accuracy**.

---

## Completeness Rules for ERDs

To produce valid and functional ERDs, adhere to these core rules:

### 1. **Primary Keys**
- Every entity type must have a primary key.
- For weak entity types:
  - The primary key must include:
    - **Borrowed attributes** from the parent entity type.
    - A **local key** unique to the weak entity type.

**Example**:
- **Room** borrows `BldgId` from **Building** and combines it with `RoomNo` to create a composite primary key:
  ```plaintext
  Primary Key = BldgId + RoomNo
  ```

### 2. **Object Names**
- Entity type names must be **unique** within the ERD.
- Attribute names must be **unique** within each entity type.
- Fully qualified names are constructed as:
  ```plaintext
  EntityTypeName.AttributeName
  ```

### 3. **Cardinalities**
- Every relationship must specify **minimum** and **maximum** cardinalities.

**Example**:
- **Missing Minimum Cardinality**:
  - The relationship `Supervises` may lack minimum cardinality near the crow’s foot symbol.

### 4. **Entity Participation in Relationships**
- All entity types should participate in at least one relationship.
- Non-participating entities:
  - Typically indicate omissions in the ERD.
  - **Exception**: Non-participating entities are permissible in rare, specialized cases.

---

## Common Violations of Completeness Rules

### Example ERD Errors:
1. **Missing Primary Key**:
   - The `Student` entity type lacks a primary key (e.g., `StdNo`).
2. **Unspecified Relationship**:
   - The `Supervising` relationship lacks minimum cardinality.
3. **Disconnected Entity**:
   - The `Course` entity type does not participate in any relationships.

**Corrections**:
- Use **business requirements** to identify errors and fill in missing details. For instance:
  - Specify `StdNo` as the primary key of `Student`.
  - Connect `Course` to `Offering` via a relevant relationship.

---

## Naming Consistency Rules

1. **Entity Type Names**:
   - Must be unique across the ERD.
   - Example:
     - Use `Faculty` and `Student` instead of ambiguous names like `Person`.

2. **Attribute Names**:
   - Unique within their entity type.
   - Example:
     - `Faculty.FacName` vs. `Student.StdName`.

3. **Relationship Names**:
   - Uniqueness is not strictly required but is **recommended** to ensure clarity.

---

## Why Do Completeness Rules Have Limitations?

### Similar to Syntax Rules for Programming
- Absence of syntax errors ≠ Correct program behavior.
- Likewise, absence of notation errors ≠ Effective data representation.

### Practical Example: Choosing a Primary Key
- **Diagram Rule**: Any attribute can be used as a primary key, as long as it fulfills the technical requirement of uniqueness.
- **Real-World Limitation**: Certain attributes (like government IDs) may introduce issues like:
  - Privacy violations.
  - Inaccuracies due to human error or fraud.

---

## Key Takeaways

1. **Completeness Rules**:
   - Prevent errors like missing primary keys, incorrect cardinalities, or unconnected entities.
   - Help create ERDs free of **notation issues**.

2. **Limitations of Rules**:
   - They cannot assess the **semantic quality** of primary keys or relationships.
   - Validating the appropriateness of primary keys requires deeper understanding of **business requirements**.

3. **Practical Examples**:
   - Missing local keys in weak entity types violate the primary key rule.
   - Failing to connect entities compromises the usefulness of an ERD for real-world queries.

By mastering these rules, you’ll ensure your ERDs are **technically correct** and ready for further refinement in Modules 8 and 9, where design quality and alignment with business needs take center stage.