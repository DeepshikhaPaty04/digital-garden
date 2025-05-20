---
{"dg-publish":true,"permalink":"/cybersecurity/try-hack-me/thm-web-fundamentals/02-introduction-to-web-hacking/2-10-sql-injection/task-4-sql-injection/"}
---


- manipulate the backend code to perform some illegal action
- use case - authentication and login bypass
- In the login bypass we will test the input fields(username and password) for sql injection vulnerability.
- Once confirmed we will apply a generic sql injection payload `' or 1=1-- ` (generic payload)
- ![attachments/Pasted image 20250516143659.png|700](/img/user/Deloitte/attachments/Pasted%20image%2020250516143659.png)
- ![attachments/Pasted image 20250516143742.png|700](/img/user/Deloitte/attachments/Pasted%20image%2020250516143742.png)
- THREE types of SQLi :
  1. General
  2. Blind based 
     - In this vulnerability, you have to blindly used different different payloads and analyze website behaviour to confirm the sqli   
  3. Time based 
     - In this vuln, you hv to depend on website's reload time to confirm the sqli

---

## **SQL Injection Types**

1. **In-Band** – Direct data retrieval via same channel (e.g., in the browser).
2. **Blind** – No direct data shown, relies on inference (e.g., page behavior).
3. **Out-of-Band** – Uses separate channel for data exfiltration (e.g., DNS requests).