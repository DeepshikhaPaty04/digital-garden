---
{"dg-publish":true,"permalink":"/cybersecurity/try-hack-me/thm-web-fundamentals/02-introduction-to-web-hacking/2-10-sql-injection/task-1-brief/"}
---

## **SQL Injection (SQLi) – Quick Notes**

- **What:** SQLi is a vulnerability where malicious SQL queries are injected into user inputs.
- **Risk:** Can lead to data theft, data manipulation, bypassing logins, or full database compromise.
- **Cause:** Poor input validation and direct inclusion of user input in SQL queries.
- **Impact:** **One of the oldest** and most **severe web vulnerabilities**.

---
## Important Contents:

1. **Databases & SQL Basics**
    
    - Databases store data (e.g., MySQL, PostgreSQL).
    - SQL used to query databases.
    - Basic SQL commands: `SELECT`, `INSERT`, `UPDATE`, `DELETE`.
        
2. **Detecting SQLi**
    
    - Input fields behaving oddly with `' OR 1=1--`, `'`, or `' AND '1'='1'`.
    - Errors or unexpected results in page responses.
        
3. **Exploiting SQLi**
    
    - Use payloads like `' OR 1=1--` to bypass logins.
    - Union-based, error-based, blind SQLi, time-based methods.
        
4. **Preventing SQLi**
    
    - **Use Prepared Statements / Parameterized Queries**.
      - Separates SQL code from data input — user input is treated **only as data**, never as part of the SQL command.
      - Example : Python: `cursor.execute("SELECT * FROM users WHERE id = %s", (user_id,))`
    - Input validation and sanitization.
      - **Input validation:**
        - Check input format (e.g., must be email, number, etc.)
        - Reject unexpected characters/types
      - **Sanitization:**
        -  Escape dangerous characters (less effective than prepared statements, but still helpful)
    
    - Use Web app firewalls (WAFs).
      - Detects and blocks common SQLi payloads at the HTTP layer.
      - Acts as an additional layer of defense.