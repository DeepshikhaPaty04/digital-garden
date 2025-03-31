---
{"dg-publish":true,"permalink":"/sql/02-basic-queries/","tags":["database_vs_dbms","RDBMS","delete","update","create","select","drop","insert"]}
---

Date: 28 Mar 2025

---
### Database vs DBMS
-  ![attachments/Pasted image 20250328090225.png](/img/user/SQL/attachments/Pasted%20image%2020250328090225.png)
## **What is RDBMS?**

- An RDBMS stores data in a **tabular format**, using rows and columns.
- It maintains **relationships** between tables using keys (Primary Key, Foreign Key, etc.).
- Ensures **data integrity, consistency, and security**.
    

## **Examples of Databases**

### **RDBMS**
- **MySQL**
- **Oracle**
- **SQLite**
- **PostgreSQL**
- **MaxDB**
- **Firebird**
    
### **NoSQL Databases**
- **MongoDB** (Document-oriented)
- **Redis** (Key-value store)

---

## **Why MySQL?**

- One of the **most popular** relational database management systems.
- Open-source and widely **used for web applications**.
- **Scalable, reliable, and secure**.
- Supports **ACID (Atomicity, Consistency, Isolation, Durability) compliance**.
- Manages **large datasets efficiently**.
    

### **SQL vs MySQL**

|**Feature**|**SQL**|**MySQL**|
|---|---|---|
|Definition|Structured Query Language|RDBMS that uses SQL|
|Purpose|Language used to interact with databases|Software that manages databases using SQL|
|Managed By|ANSI/ISO Standard|Oracle Corporation|
|Type|Language|Software|

📌[Know more about MySQL](https://dev.mysql.com/doc/refman/8.0/en/tutorial.html)

---
## How to CREATE, USE and DROP a database

 - Listing all Existing Database
	`SHOW DATABASES;`
- Creating a new database
	`CREATE DATABASE store_db;`
- Working with a Datebase
	`USE store_db;`
- Deleting a database
	`DROP store_db;`
- To know, inside which database you are
	`SELECT database();`
- To get information about the created table
	`DESC students;`
- 
## CREATE table
- a table is a collection of related data held in a table format within a database.
- `CREATE TABLE students(`
	`id INT,`
	`name VARCHAR(100));`
	
## INSERT table
- `INSERT INTO students(id,name) VALUES (101, "Rahul");`
- `INSERT INTO students VALUES (101, "Rahul");`  --> (if you are inserting values in the original sequence as that of the table, then no need to mention the column name)
- `INSERT INTO students VALUES (101, "Rahul"), (102, "Meghna"), (103, "Sitesh");`

## SELECT table
- `SELECT * FROM table_name;`
- `SELECT column_name FROM students;`
- `SELECT column_name FROM students WHERE id=103;`

## UPDATE query
- `UPDATE students
	`SET contact = 12345`
	`WHERE id = 101;`

## DELETE data from table
-  `DELETE FROM students WHERE name='Raju';`

## DROP whole table
- `DROP students;`
