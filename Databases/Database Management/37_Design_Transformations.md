# Refining ERDs – Transformation Techniques

---

## Opening Question: What is the Difference Between Attribute Expansion and Entity Type Expansion?

1. **Attribute Expansion**:
   - Involves replacing an **attribute** of an entity type with a new **entity type** in a one-to-many relationship.
   - Used when more information about the attribute is required.
   - Example: Expanding `EmpNo` (Employee Number) in `Reading` to an `Employee` entity type with additional attributes like `EmpName` and `EmpDept`.

2. **Entity Type Expansion**:
   - Involves splitting an **entity type** into two entity types in a one-to-many relationship, to represent a finer level of detail.
   - There is no original attribute to expand; instead, structure and hierarchy are introduced.
   - Example: Expanding `Rate` into `RateSet` (for a set of rates) and `Rate` (for specific rates) in a water utility system.

**Key Difference**: Attribute expansion starts with an attribute, while entity type expansion begins with a pre-existing entity type.

---

## Lesson Objectives

1. Understand the iterative nature of data modeling and the importance of generating and evaluating **alternative designs**.
2. Learn four transformation techniques:
   - **Attribute Expansion**.
   - **Compound Attribute Split**.
   - **Entity Type Expansion**.
   - **Weak-to-Strong Entity Type Transformation**.
3. Recognize the business situations where each transformation is applicable.

---

## The Importance of Generating Alternative Designs

Data modeling is rarely a one-shot process. Instead, it evolves through:
1. **Preliminary Designs**:
   - Develop an initial ERD based on problem narratives.
2. **Refinement Cycles**:
   - Use transformations to explore feasible alternatives.
   - Evaluate alternatives against user requirements.
   - Gather additional input from stakeholders as needed.
3. **Finalization**:
   - Select the design that best satisfies requirements and minimizes redundancy.

---

## Transformation Techniques

### 1. **Attribute Expansion**

**Purpose**:
- Expand an attribute into a full-fledged entity type when more data about the attribute is needed.

**Example**:
- **Before Expansion**:
  - `Reading` has `EmpNo` as an attribute.
- **After Expansion**:
  - Create an `Employee` entity type with attributes like:
    - `EmpNo` (PK), `EmpName`, `EmpDept`.
  - Establish a one-to-many relationship between `Reading` and `Employee`.

**Key Considerations**:
- Requires careful evaluation of minimum cardinalities.
- Useful when attributes like `EmpNo` need richer descriptive information.

---

### 2. **Compound Attribute Split**

**Purpose**:
- Split compound attributes containing multiple components into separate attributes to simplify searches and enable better standardization.

**Example**:
- **Before Split**:
  - `Address` in `Customer` is a compound attribute combining:
    - `Street`, `City`, `State`, and `PostalCode`.
- **After Split**:
  - Create separate attributes:
    - `Street`, `City`, `State`, `PostalCode`.

**Challenges**:
- Standardizing components can be difficult, especially when formats vary by region or country.
- Pre-existing systems may have incomplete or inconsistent data in compound attributes.

---

### 3. **Entity Type Expansion**

**Purpose**:
- Split an entity type into two levels to record more granular details or add hierarchy.

**Example 1: Rate Expansion**:
- **Before Expansion**:
  - `Rate` records all consumption levels.
- **After Expansion**:
  - Create `RateSet` for sets of rates.
  - Establish a one-to-many relationship between `RateSet` and `Rate`.

**Example 2: Position Expansion**:
- **Before Expansion**:
  - `Position` is a single-level entity.
- **After Expansion**:
  - Split into `JobClass` and `Position`, where `Position` depends on `JobClass`.

**Notes**:
- Identification dependency may or may not apply.

---

### 4. **Weak-to-Strong Entity Type Transformation**

**Purpose**:
- Convert a weak entity type into a strong entity type to simplify referencing and enhance flexibility.

**Example**:
- **Before Transformation**:
  - `Room` depends on `Building` (weak entity type), with a composite primary key of `BuildingID + RoomNo`.
- **After Transformation**:
  - Add `RoomID` as a new primary key for `Room`, making it a strong entity type.
  - Maintain `BuildingID + RoomNo` as a unique constraint for backward compatibility.

**When to Use**:
- Particularly useful for associative entity types.
- Simplifies table references during database implementation.

---

## Key Takeaways

1. **Iterative Process**:
   - Data modeling involves multiple refinement cycles to produce a robust and efficient design.

2. **Transformation Techniques**:
   - Attribute Expansion: Converts an attribute into an entity type.
   - Compound Attribute Split: Breaks compound attributes into discrete components.
   - Entity Type Expansion: Splits an entity type into two, introducing hierarchy or finer detail.
   - Weak-to-Strong Conversion: Converts weak entity types into strong entity types for easier referencing.

3. **Application**:
   - Use transformations judiciously, balancing simplicity and user requirements.

With these techniques, you can better refine your ERDs to align with complex business scenarios while maintaining clarity and precision. The next lesson will focus on assessing trade-offs between alternatives to create models that best address organizational needs.