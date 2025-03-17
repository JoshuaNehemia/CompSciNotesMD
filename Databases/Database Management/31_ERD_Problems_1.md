# Problem Solving with ERD Notation

---

## Opening Question: How Does an ERD Support Business Policies?

An Entity Relationship Diagram (ERD) supports business policies by:

1. **Capturing Business Rules**:
   - **Primary Keys**: Ensure unique entity identification, a critical requirement for clear and consistent communication within and across organizational units.
   - **Relationships**: Illustrate connections between entities, reflecting dependencies and interactions.
   - **Cardinalities**: Impose constraints (e.g., mandatory or optional participation), directly reinforcing business rules such as policy restrictions or operational requirements.

2. **Promoting Efficiency**:
   - Business rules embedded in ERDs help stakeholders streamline processes by clearly delineating rules, restrictions, and relationships.
   - For instance, an ERD might restrict orders to customers with valid records, reducing data inconsistencies.

3. **Enhancing Communication**:
   - An ERD serves as a shared framework, enabling stakeholders from different departments to collaborate more effectively by visualizing organizational policies.

By creating ERDs, you participate in defining and enforcing business policies, which can improve organizational efficiency and clarity.

---

## Lesson Objectives

1. Apply problem-solving skills to create basic ERDs using **Crow’s Foot Notation**.
2. Use relationships, primary keys, and cardinalities to reflect **business rules**.
3. Build confidence in modeling scenarios using tools such as the **ER Assistant**.

---

## Problem Highlights

### **Problem 1: Customer and Order Relationship**

**Scenario**:
- Model a one-to-many relationship where a **Customer** can place multiple **Orders**, but each order must be associated with one customer.
- Include specific attributes and define cardinalities.

#### Key Steps:
1. **Create Entity Types**:
   - **Customer**: Attributes include `CustNo` (PK), `CustFirstName`, `CustLastName`, `CustStreet`, `CustCity`, `CustState`, `CustZip`, and `CustBal`.
   - **Order**: Attributes include `OrdNo` (PK), `OrdDate`, `OrdName`, `OrdStreet`, `OrdCity`, `OrdState`, and `OrdZip`.

2. **Define Relationship**:
   - Connect **Customer** and **Order** with a one-to-many relationship named **Places**.

3. **Set Cardinalities**:
   - **Customer → Order**:
     - Minimum: **0** (a customer may not place orders).
     - Maximum: **many** (a customer can place multiple orders).
   - **Order → Customer**:
     - Minimum: **1** (an order must be associated with a customer).
     - Maximum: **1** (an order can only belong to one customer).

4. **Specify Data Types**:
   - Use appropriate data types:
     - `CustNo`, `OrdNo`: Integer.
     - `CustFirstName`, `CustLastName`: VarChar.
     - `OrdDate`: Date or TimeStamp.

#### ERD Solution:
The **Customer** entity connects to the **Order** entity via the **Places** relationship with the cardinalities indicated by **Crow’s Foot Notation** (circle for zero, perpendicular line for one).

---

### **Problem 2: Adding Employee and Self-Referencing Relationship**

**Scenario**:
- Extend the model with an **Employee** entity linked to **Order** and include a **self-referencing relationship** for employee hierarchies.

#### Key Steps:
1. **Add Employee Entity**:
   - Attributes include:
     - `EmpNo` (PK), `EmpFirstName`, `EmpLastName`, `EmpPhone`, `EmpEmail`, `EmpCommRate` (commission rate), and `EmpDeptName`.

2. **Define Relationships**:
   - **Employee ↔ Order**:
     - Relationship Name: **Takes**.
     - Cardinalities:
       - **Order → Employee**: Optional (`0:M` - an order may not have an employee associated).
       - **Employee → Order**: Optional (`0:M` - an employee may not handle any orders).
   - **Employee ↔ Employee**:
     - Relationship Name: **Manages** (self-referencing).
     - Cardinalities:
       - Both directions are optional (`0:M` - an employee may not have subordinates or a manager).

3. **Specify Data Types**:
   - `EmpNo`: Integer.
   - `EmpCommRate`: Decimal.
   - `EmpFirstName`, `EmpLastName`: VarChar.

#### ERD Solution:
- The **Employee** entity participates in:
  - A one-to-many relationship with **Order**.
  - A self-referencing relationship to represent managerial hierarchies.

---

## Summary of Key Concepts

1. **Problem-Solving Skills**:
   - Use ERD tools to build and extend simple models.
   - Ensure cardinalities, attributes, and relationships accurately reflect business rules.

2. **Importance for Business Policies**:
   - ERDs represent and enforce business rules through:
     - **Primary Keys** for entity identification.
     - **Relationships** for interaction modeling.
     - **Cardinalities** for operational constraints.

3. **Building Confidence**:
   - Practice iterative problem-solving to refine both technical and conceptual modeling skills.

Through hands-on application, you develop the expertise to create ERDs that capture organizational policies and streamline business processes. This prepares you for more complex scenarios in future lessons and modules.