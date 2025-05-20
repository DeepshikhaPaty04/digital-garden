---
{"dg-publish":true,"permalink":"/cybersecurity/try-hack-me/thm-web-fundamentals/02-introduction-to-web-hacking/2-10-sql-injection/task-3-sql/"}
---

## **SQL Basics: Key Commands & Usage**

### What is SQL?
- **SQL** (Structured Query Language): Used to **query, update, insert, and delete** data in a database.
- Case-insensitive.
- This guide uses **MySQL syntax** (similar in others).
    
---

## **SELECT Statement**

- `SELECT * FROM users;` → Get **all columns** from `users`.
- `SELECT username, password FROM users;` → Get **specific columns**.
- `SELECT * FROM users LIMIT 1;` → Return **first row** only.
- `SELECT * FROM users LIMIT 1,1;` → **Skip 1**, return next row.
    

---

### **WHERE Clause**

- `WHERE column = 'value'` → Match exact.
- `!=` → Not equal.
- `OR` / `AND` → Combine conditions.
- `LIKE` → Pattern matching:
    - `'a%'` → Starts with 'a'
    - `'%n'` → Ends with 'n'
    - `'%mi%'` → Contains 'mi'
        

---

## **UNION Statement**

- Combines **results from 2+ SELECTs**.
- Columns must match in **number, type, and order**.

`SELECT name, address FROM customers UNION SELECT company, address FROM suppliers;`

---

## **INSERT Statement**

- Adds new row to a table.
`INSERT INTO users (username, password) VALUES ('bob', 'password123');`

---

## **UPDATE Statement**

- Modifies existing data.
    
`UPDATE users SET username='root', password='pass123' WHERE username='admin';`

---

## **DELETE Statement**

- Removes rows.

`DELETE FROM users WHERE username='martin'; DELETE FROM users;  -- Deletes **all** rows (no WHERE clause)`