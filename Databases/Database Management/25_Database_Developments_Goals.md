# Database Development and Entity Relationship Diagrams (ERDs)

---

## Opening Question: Why Is Database Development Challenging and Exciting?

Database development is both challenging and exciting because:
1. **Ambiguity and Creativity**:
   - Unlike query formulation, database development involves subjective decision-making and creative problem-solving to balance various organizational needs.
   
2. **Long-Term Organizational Impact**:
   - While query formulation aids short-term insights, well-designed databases create **foundational resources** for an organization. They define vocabulary, enforce business rules, and ensure data quality.
   
3. **Facilitating Change**:
   - Databases unify different parts of an organization by providing shared vocabulary and common business rules, potentially transforming workflows and productivity.

---

## Lesson Objectives

1. Understand the **goals of database development** and its role in the larger context of information systems.
2. Gain a foundational understanding of entity relationship diagrams (ERDs) as a notation tool for database design.
3. Position skills from this module within the overall database development process.

---

## Database Development in Information Systems

### Role of Databases
- Databases provide **long-term memory** for information systems, holding **entities** and their **relationships**.
- Example: A **student loan system database** might store:
  - **Entities**: Students, loans, payments.
  - **Relationships**: Loans linked to students; payments linked to loans.

### Information System Components
Beyond databases, information systems include:
- **People**: Users and administrators.
- **Procedures**: Business workflows.
- **Input/Output Data**: User interactions and reporting.
- **Software**: Applications and database management systems (DBMS).
- **Hardware**: Servers, storage devices, and networks.

---

## Goals of Database Development

1. **Common Vocabulary**:
   - Databases act as a shared dictionary for organizations, facilitating communication across teams.
   - Achieving this goal requires compromise, as different departments often have varying priorities and interpretations.

2. **Support Organizational Policies**:
   - Databases enforce **business rules** through integrity constraints.
   - Example:
     - Business Rule: "An order must precede a shipment."
     - Enforced by: Constraints ensuring an order exists before a shipment is added.

3. **High-Quality Data**:
   - Just as product quality is critical in manufacturing, **data quality** determines the success of information systems.
   - Poor data quality can result in:
     - Miscommunication with customers.
     - Incorrect identification of repeat customers.
     - Errors in sales reporting and customer issue resolution.

4. **Efficient Access**:
   - Even a well-designed database will fail if it is too slow or inefficient for users.
   - However, optimizing performance should not compromise **data quality** or **business rules**.

---

## Database Development Process

The goal is to produce an **operational database** for an information system. This involves multiple phases:

### Phases of Development
1. **Conceptual Data Modeling**:
   - Define the **high-level structure** of the database.
   - Capture entities, relationships, and attributes without concern for implementation.
   - Tools: Entity Relationship Diagrams (ERDs).

2. **Logical Database Design**:
   - Translate the conceptual model into a **relational schema** using primary keys, foreign keys, and constraints.

3. **Distributed Database Design**:
   - Determine how to distribute the database across multiple locations.
   - Consider factors such as network traffic and data consistency.

4. **Physical Database Design**:
   - Optimize the database for performance based on the DBMS and query patterns.

---

## Focus of This Course
This course emphasizes:
1. **Conceptual Data Modeling**:
   - Covered in **Modules 6 and 7** using **ERD notation**.
2. **Logical Database Design**:
   - Covered in **Modules 8 and 9** to transform ERDs into relational designs.

---

## Why Use ERDs?

ERDs serve as a powerful tool for:
1. **Visualizing Data**:
   - They show entities, relationships, and attributes in a clear, easy-to-understand diagram.
2. **Unifying Teams**:
   - A shared visual representation makes it easier to align stakeholders on database goals.

---

## Key Takeaways

1. **Databases** are vital components of information systems, serving as long-term memory for entities and relationships.
2. **Goals of Database Development** include:
   - Establishing a common vocabulary.
   - Enforcing business rules.
   - Ensuring high-quality data.
   - Delivering efficient access.
3. **Creative Problem-Solving**:
   - Database development is subjective, requiring compromises to balance competing organizational needs.

In the next lessons of this module, you will explore the notation of entity relationship diagrams, providing essential skills for **conceptual data modeling**. Through these tools, you’ll gain the ability to craft databases that align with organizational goals and foster transformation.