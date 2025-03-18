# Transformations for Retaining History in Data Models

---

## Opening Question: What History Transformations Are Important in Data Warehouse Design?

### Key Transformations:
1. **Attribute History Transformation**:
   - Adds historical records for selected attributes, enabling detailed tracking over time.
   - Example: Tracking employee titles or customer statuses.

2. **One-to-Many Relationship History Transformation**:
   - Adds history to relationships by creating an associative entity type to record changes over time.
   - Example: Retaining historical ownership of assets, such as vehicles or meter assignments.

3. **Limited History Transformation**:
   - Retains a fixed, limited number of historical states within the same entity.
   - Example: Keeping only the current and previous values of employee titles, rather than all history.

These transformations are crucial in **data warehouse designs** to support tactical and strategic decision-making, ensuring access to historical trends and insights.

---

## Lesson Objectives

1. Learn transformations for retaining **history** in ERDs, expanding your ability to model evolving data over time.
2. Explore **reverse transformations** to simplify complex designs.
3. Understand how to apply and evaluate history transformations for specific business scenarios.

---

## Refining Data Models with History Transformations

### Attribute History Transformation

**Purpose**:
- Record the history of changes to attributes over time.

**Example: Employee Title History**:
- **Before Transformation**:
  - `Employee` has an `EmpTitle` attribute.
- **After Transformation**:
  - Replace `EmpTitle` with a new `EmpTitleHistory` entity type.
  - Relationship: `HasTitle` (1:M) between `Employee` and `EmpTitleHistory`.
  - Attributes of `EmpTitleHistory`:
    - `EmpNo` (borrowed from `Employee`), `VersionNo` (to differentiate versions), `BeginDate`, `EndDate`.

**Similar Example: Student Major History**:
- Replace `StdMajor` with `MajorHistory`, which includes:
  - Primary Key: Combination of `StdNo` and `VersionNo`.
  - Attributes: `BeginDate`, `EndDate`.

---

### One-to-Many Relationship History Transformation

**Purpose**:
- Preserve historical records for relationships, such as assignments or ownerships.

**Example: Meter Assignment**:
- **Before Transformation**:
  - One-to-Many `Uses` relationship between `Customer` and `Meter`.
- **After Transformation**:
  - Create an associative entity type, `MeterAssignment`, with:
    - Primary Key: Combination of `CustNo`, `MeterNo`, and `VersionNo`.
    - Attributes: `BeginDate`, `EndDate`.
  - Relationships:
    - `Customer` → `MeterAssignment` (1:M).
    - `MeterAssignment` → `Meter` (M:1).

**Why Necessary?**:
- Ensures that even if the same meter is reassigned to different customers, historical accuracy is maintained.

---

### Limited History Transformation

**Purpose**:
- Track a **fixed number of states** for attributes, rather than an unlimited history.

**Example: Employee Title History (Limited)**:
- Replace `EmpTitle` with:
  - `EmpCurrTitle` (current title).
  - `EmpPrevTitle` (previous title).
- Add attributes for change dates:
  - `CurrBeginDate`, `PrevBeginDate`, `PrevEndDate`.

**When to Use**:
- Appropriate when only the most recent changes are relevant.
- Reduces complexity and storage requirements compared to unlimited history transformations.

---

## Simplifying Models with Reverse Transformations

Reverse transformations are used to simplify overly complex designs. They revert earlier expansions or refinements. 

### Prominent Reverse Transformations:
1. **Contract Entity Type**:
   - Opposite of attribute expansion.
   - Combine an entity type back into an attribute of its parent entity.
   
2. **Combine Attributes**:
   - Opposite of compound attribute splitting.
   - Reintegrate split components into a single compound attribute.
   
3. **Contract Entity Type Structure**:
   - Opposite of entity type expansion.
   - Merge related entities back into a single entity type.

4. **Strong Entity Type to Weak Entity Type**:
   - Opposite of weak-to-strong transformation.
   - Restore a weak entity type relationship for simpler referencing.

5. **Remove History**:
   - Opposite of adding history.
   - Used when tracking historical data is no longer necessary or valuable.

---

## Business Context: Why History Transformations Matter

- **Operational Databases**:
  - Focus on current data for real-time applications.
  - History transformations are less emphasized unless legal or operational requirements demand historical records.

- **Data Warehouses**:
  - Built specifically to store and analyze large amounts of historical data.
  - History transformations are critical for:
    - Strategic decision-making (e.g., sales trends, customer retention).
    - Tactical analysis (e.g., employee performance, product lifecycles).
  - Unlimited history transformations are particularly useful for tracking important transactions like orders and invoices.

---

## Key Takeaways

1. **Transformations for Retaining History**:
   - Attribute History: Tracks evolving attribute data.
   - Relationship History: Tracks changes in relationships over time.
   - Limited History: Records a fixed number of states for attributes.

2. **Reverse Transformations**:
   - Simplify overly complex models by undoing refinements and expansions.

3. **Importance in Data Warehouses**:
   - History retention is essential for meaningful analysis and decision-making.
   - Transformation techniques directly support the dominant design patterns of data warehouses, ensuring robust historical data management.
