---
{"dg-publish":true,"permalink":"/cybersecurity/try-hack-me/thm/introduction-to-web-hacking/idor/"}
---

[Access & try solving the room](https://tryhackme.com/room/idor)

# IDOR

- IDOR stands for `Insecure Direct Object Reference` and is a type of **access control vulnerability**
- **IDOR (Insecure Direct Object Reference)** happens when a website or app **lets users access something directly (like someone’s info or file)** just by changing a number or ID in the URL — **without checking if the user is allowed to see it**.
- IDOR is listed under the **Broken Access Control** category in the OWASP Top 10, one of the most critical security issues in web applications.


### Why It's Dangerous:

- **Privacy breach**: Access personal info of other users.
- **Data modification**: Change or delete other users' data.
- **Privilege escalation**: Gain unauthorized admin access.


## **Encoded IDs**

- When a website moves data from one page to another (like through:
    - **Forms (POST data)**
    - **URLs (query strings)**
    - **Cookies**

- Developers often **encode the data** first.

- **Encoding** turns data (like numbers, text, etc.) into a format that is safe to send.
- It ensures the **web server understands** the data properly.
- It is **not encryption** — anyone can decode it!

- **Base64** is the most common encoding used on websites.
- It turns normal data into **letters and numbers**, like:
    - `a-z`, `A-Z`, `0-9`, and sometimes '=' 


> [!NOTE]
> 
> They use it for **data formatting**, _not security_. Here’s what Base64 does:
> - Makes binary or special characters safe to send in:
>     - URLs
>     - Cookies
>     - Web forms
> - Helps **transmit data reliably** — like packing it neatly in a box.
>     
> But it doesn’t **hide** or **protect** the content.


## **Hashes IDs**

- Hashed IDs are a little bit more complicated to deal with than encoded ones
- common algorithm used for hashing IDs is md5
- Hashing turns something (like a number or word) into a **fixed-length code**.
- It **can’t be easily reversed**, unlike Base64.
- Same input always gives the same output.
    - Example: `md5(123)` will always be `202cb962ac59075b964b07152d234b70`

### Why do websites use hashed IDs?

- To **hide real values** like user IDs or file names.
- So attackers can’t easily guess what to access next.
- It adds a **layer of difficulty**, but **not full security**.

## **Unpredictable IDs**

Sometimes, websites use **random or hidden IDs**, so you can’t guess them easily.

But to check for **IDOR (Insecure Direct Object Reference)**:
1. **Create two accounts** (like Account A and Account B).
2. While logged in to Account A, try using the **ID from Account B** in the URL or request.
3. If you can see **Account B’s data** while logged into Account A — 🎯 **that’s an IDOR vulnerability**.


✅ Even if the ID looks random, if the site **doesn't check permissions properly**, you can still **access things you shouldn’t**.


## Where we can find IDOR

IDOR issues aren’t always right there in the **URL bar**.
Sometimes they are hidden in places like:

- **AJAX requests** (background requests your browser makes)
- **JavaScript files** (code the website uses)
- **Old or hidden parameters** used during development but still live

IDOR bugs can be hidden in background activity or unused parameters.  
You just have to **dig a little deeper** to find them.

 