# Non-Procedural Access

## Introduction
Non-procedural access allows users to retrieve database information without specifying the exact implementation details. This method significantly reduces the complexity of database queries and improves software development efficiency.

## Objectives
By the end of this lesson, you should be able to:
- Explain the importance of non-procedural access.
- Discuss common features in SQL client tools (e.g., Oracle SQL Developer, pgAdmin).
- Understand the role of database programming languages.

## What is Non-Procedural Access?
- **Definition:** Users specify what data to retrieve, but not how to retrieve it.
- **Key Advantage:** Eliminates the need for loops (`for`, `while`, etc.).
- **Efficiency:** Reduces lines of code by a factor of 100 compared to procedural access.
- **Impact:** Enhances productivity in data-driven software development.

## Standard Tool: SQL `SELECT` Statement
- SQL provides a non-procedural way to retrieve database records.
- Most DBMSs offer SQL clients to execute queries.

### SQL Clients for Database Retrieval
#### **1. Oracle SQL Developer**
- Allows connection to Oracle databases.
- Features a worksheet tab for writing and executing SQL statements.
- Supports:
  - Statement execution
  - Query history
  - Commit/rollback changes
  - SQL editing tools

#### **2. pgAdmin (PostgreSQL Client)**
- Open-source database client for PostgreSQL.
- Provides a query tool for executing SQL statements.
- Supports:
  - Query execution
  - Statement history
  - Saving and editing SQL queries

## Graphical Query Tools
- Some DBMSs offer graphical tools for database retrieval.
- Example: Oracle SQL Developer provides a **Query Builder** for graphical query specification.
- PostgreSQL’s **pgAdmin** does not include a built-in graphical tool, but third-party tools are available.

## Limitations of Non-Procedural Access
- Not suitable for **complex applications** (e.g., shopping carts, data mining).
- Cannot fully replace procedural logic for **data-intensive applications**.

## Database Programming Languages
To support advanced database operations, DBMSs provide programming languages with embedded SQL:
- **Oracle PL/SQL**
- **PostgreSQL PL/pgSQL**

### Features of Database Programming Languages
- Establish database connections.
- Execute SQL queries and process results.
- Map programming variables to database columns.
- Handle SQL exceptions.

## Conclusion
- **Non-procedural access** is essential for efficient data retrieval.
- **SQL** enables users to interact with databases without procedural logic.
- **Graphical tools** enhance usability for business analysts.
- **Database programming languages** provide additional functionality for complex applications.
