# SQL Overview

## Table of Contents

- [SQL Overview](#sql-overview)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Trivia Questions](#trivia-questions)
  - [The Evolution of SQL](#the-evolution-of-sql)
    - [Origins of SQL](#origins-of-sql)
    - [The Naming History](#the-naming-history)
      - [Fun Fact](#fun-fact)
  - [SQL Standards and Compliance](#sql-standards-and-compliance)
    - [The Role of Standards Organizations](#the-role-of-standards-organizations)
    - [Conformance Testing and Its Impact](#conformance-testing-and-its-impact)
      - [Challenges](#challenges)
    - [Comparison with Web Standards](#comparison-with-web-standards)
      - [Implications](#implications)
  - [Contexts of Using SQL](#contexts-of-using-sql)
    - [Standalone SQL](#standalone-sql)
    - [Embedded SQL](#embedded-sql)
  - [Types of SQL Statements](#types-of-sql-statements)
    - [Data Definition Language (DDL)](#data-definition-language-ddl)
    - [Data Manipulation Language (DML)](#data-manipulation-language-dml)
    - [Data Control Language (DCL)](#data-control-language-dcl)
      - [Note](#note)
  - [Implications of Weak Conformance](#implications-of-weak-conformance)
      - [Perspective](#perspective)
      - [Tip](#tip)
  - [Conclusion](#conclusion)

---

## Introduction

In this lesson, we'll explore the basics of query formulation in SQL, one of the most critical skills in database management. We'll also examine the significance of standards compliance in SQL and how it compares to web standards like HTML5.

## Trivia Questions

1. **Why is SQL sometimes pronounced "sequel"?**

2. **How does compliance with the SQL standard compare to compliance with web standards such as HTML5?**

These questions are more than just trivia—they touch on the history of SQL and the commercial impact of standards in technology.

## The Evolution of SQL

### Origins of SQL

SQL, or **Structured Query Language**, has evolved over **40 years** and serves as a comprehensive language for:

- **Database Definition**
- **Control**
- **Manipulation**

Previously, we used the `CREATE TABLE` statement—a part of SQL's Data Definition capabilities. Now, we'll focus on the `SELECT` statement in, which is central to data manipulation.

### The Naming History

- **SQUARE Language:** SQL began as the **SQUARE** (Specifying Queries as Relational Expressions) language in IBM's **System R project**. It was mathematical and abstract.
- **SEQUEL:** To make it more user-friendly, IBM researchers revised SQUARE into **SEQUEL** (Structured English Query Language) after human factors experiments.
- **Legal Issues:** Legal challenges forced IBM to drop the vowels, leading to the name **SQL**.
- **Pronunciation:** Due to this history, many professionals, especially from the 1970s, pronounce SQL as "**sequel**".

#### Fun Fact

Despite IBM's significant role, it wasn't the first to commercialize SQL!

## SQL Standards and Compliance

### The Role of Standards Organizations

To address the **commercial confusion** of multiple SQL variants in the early days, several organizations stepped in:

- **ANSI** (American National Standards Institute)
- **ISO** (International Organization for Standardization)
- **IEC** (International Electrotechnical Commission)

These bodies worked to standardize SQL, enhancing its features and ensuring a unified language specification.

### Conformance Testing and Its Impact

- **Pre-1996:** The **National Institute of Standards and Technology (NIST)** conducted conformance tests to ensure software portability across government systems.
- **Post-1996:** Independent testing ceased, leaving **DBMS vendors** to self-certify compliance.

#### Challenges

- **Core SQL:** Even fundamental features lack uniform support across major vendors.
- **Optional Features:** There's even **greater variance**, making portability a significant challenge.

### Comparison with Web Standards

In contrast, **web standards** show strong compliance:

- **HTML5:** The standard markup language for web pages.
- **W3C Validation:** The **World Wide Web Consortium (W3C)** offers validation services to ensure compliance.
- **Acid3 Tests:** The **Web Standards Project** provides stringent compliance tests.

#### Implications

- **DBMS Industry:** Exhibits **weak conformance**, leading to reduced portability and higher switching costs.
- **Web Industry:** Strong compliance promotes interoperability and eases developer burdens.

## Contexts of Using SQL

SQL operates in two primary contexts:

### Standalone SQL

- Users submit SQL statements directly through specialized editors like **SQL Developer** or command-line interfaces.
- Ideal for **ad-hoc queries** and direct database interactions.

### Embedded SQL

- SQL statements are integrated within a host programming language (e.g., **Java**, **Visual Basic**).
- The program sends SQL commands, and the **DBMS** returns results to the application.
- Common in applications requiring dynamic database interactions.

## Types of SQL Statements

SQL is a **complete data language** encompassing:

### Data Definition Language (DDL)

- **Purpose:** Defines the structure of the database.
- **Key Statements:**
  - `CREATE`: Creates new database objects like tables and indexes.
  - `ALTER`: Modifies existing database structures.
  - `DROP`: Deletes database objects.

### Data Manipulation Language (DML)

- **Purpose:** Manages data within the schema.
- **Key Statements:**
  - `SELECT`: Retrieves data from the database.
  - `INSERT`: Adds new data.
  - `UPDATE`: Modifies existing data.
  - `DELETE`: Removes data.

### Data Control Language (DCL)

- **Purpose:** Controls access and permissions.
- **Key Statements:**
  - `GRANT`: Gives user access privileges.
  - `REVOKE`: Removes user access privileges.

#### Note

Database administrators frequently use DDL and DCL statements, while developers often focus on DML.

## Implications of Weak Conformance

- **Portability Issues:** Applications may not run seamlessly on different DBMS platforms due to proprietary extensions and lack of standard support.
- **Vendor Lock-In:** Organizations may find it costly to switch vendors, giving DBMS providers more **market power**.
- **Innovation vs. Standardization:** While vendors argue that non-conformance allows for **innovation**, it places a burden on developers to manage compatibility.

#### Perspective

- **DBMS Industry:** Prioritizes vendor control and innovation, sometimes at the expense of standard compliance.
- **Web Environment:** Emphasizes standardization to facilitate a universal and accessible web.

#### Tip

Mastering SQL requires **practice**. Hands-on experience will solidify your understanding of query formulation.

## Conclusion

SQL is a powerful but complex language with a rich history and significant industry implications. Understanding its standards, usage contexts, and the nuances of compliance will not only make you a proficient SQL user but also provide valuable insights into the broader technological landscape.

---
