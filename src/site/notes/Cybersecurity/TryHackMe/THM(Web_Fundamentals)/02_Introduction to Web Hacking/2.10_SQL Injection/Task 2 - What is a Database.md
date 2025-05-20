---
{"dg-publish":true,"permalink":"/cybersecurity/try-hack-me/thm-web-fundamentals/02-introduction-to-web-hacking/2-10-sql-injection/task-2-what-is-a-database/"}
---

## **Introduction to Databases and SQL**

### What is a Database?
- A **database** stores collections of data electronically in an organized way.
- Managed by a **DBMS** (Database Management System).
- Two main types:
    - **Relational DBMS** (focus of this room): MySQL, PostgreSQL, SQL Server, SQLite, Access.
    - **Non-Relational DBMS** (NoSQL): MongoDB, Cassandra, ElasticSearch.

---

### Database Structure

#### Multiple Databases in a DBMS:
- Example: A "shop" database may contain tables for: 
    - Products
    - Users
    - Orders
        
#### Tables:
- Each **database contains tables** to separate and organize data.
- Each table has a **unique name**.

---

### What are Tables?
#### Structure:
- **Grid-like format** of columns and rows.

#### Columns (Fields):
- Define **data type** (e.g., INTEGER, TEXT, DATE).
- Each has a **unique name** per table.
- Can be:
    - **Auto-incremented**: Automatically increases with each new row.
    - **Key field**: Unique identifier for rows (e.g., **Primary Key**).
    
#### Rows (Records):
- Each row represents a **single data entry**.
- Adding = new row, Deleting = remove row.

---
### 🔗 **Relational vs Non-Relational**

|Feature|Relational DB|Non-Relational DB (NoSQL)|
|---|---|---|
|Structure|Tables with rows & columns|No fixed structure|
|Data Relationships|Strong (via keys & foreign keys)|Weak or none|
|Flexibility|Rigid schema|Schema-less, flexible|
|Examples|MySQL, PostgreSQL, SQLite|MongoDB, Cassandra, ElasticSearch|
