---
{"dg-publish":true,"permalink":"/port-swigger/clickjacking/lab1-basic-clickjacking-with-csrf-token-protection/"}
---

Date : 12 Mar, 2025

---
[Access the lab](https://portswigger.net/web-security/clickjacking/lab-basic-csrf-protected)

> [!abstract]
> ### **Motive / Objective:**
> 
> The **goal** of this lab is to perform a **clickjacking attack**, where you trick the victim into **unknowingly clicking** on a sensitive action (like "Delete account") on a legitimate website by hiding it behind a fake, clickable UI element.
> 
> This is a **social engineering** attack that leverages **transparent iframes** to invisibly load another website behind decoy content. When the victim interacts with the fake content, they are actually clicking on the real button behind it.

1. Log in to your account on the target website. credentials: `wiener:peter`
![attachments/Pasted image 20250427105150.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427105150.png)
2. Go to the exploit server and paste the following HTML template into the **Body** section:
    
    `<style> iframe { position:relative; width:$width_value; height: $height_value; opacity: $opacity; z-index: 2; } div { position:absolute; top:$top_value; left:$side_value; z-index: 1; } </style> <div>Test me</div> <iframe src="YOUR-LAB-ID.web-security-academy.net/my-account"></iframe>`

3. Make the following adjustments to the template:
    - Replace `YOUR-LAB-ID` in the iframe `src` attribute with your unique lab ID.
    - ![attachments/Pasted image 20250427105516.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427105516.png)
    - Substitute suitable pixel values for the `$height_value` and `$width_value` variables of the iframe (we suggest 700px and 500px respectively).
    - Substitute suitable pixel values for the `$top_value` and `$side_value` variables of the decoy web content so that the "Delete account" button and the "Test me" decoy action align (we suggest 300px and 60px respectively).
    - Set the opacity value `$opacity` to ensure that the target iframe is transparent. Initially, use an opacity of 0.1 so that you can align the iframe actions and adjust the position values as necessary. For the submitted attack a value of 0.0001 will work.
    - ![attachments/Pasted image 20250427105827.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427105827.png)
4. Click **Store** and then **View exploit**.
![attachments/Pasted image 20250427120919.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427120919.png)
5. Hover over **Test me** and ensure the cursor changes to a hand indicating that the div element is positioned correctly. **Do not actually click the "Delete account" button yourself.** If you do, the lab will be broken and you will need to wait until it resets to try again (about 20 minutes). If the div does not line up properly, adjust the `top` and `left` properties of the style sheet.
6. Once you have the div element lined up correctly, change "Test me" to "Click me" and click **Store**.
![attachments/Pasted image 20250427121344.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427121344.png)
7. Click on **Deliver exploit to victim** and the lab should be solved.

![attachments/Pasted image 20250427121316.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427121316.png)



> [!summary]
> The victim unknowingly clicks on the **invisible Delete account button** while thinking they’re clicking "Click me" — leading to **account deletion**, successfully solving the lab.

---

### What is an `<iframe>`?

- An iframe is an HTML tag used to **embed another website/page** inside your page.
  `<iframe src="https://example.com/my-account"></iframe>`

- If the website allows it, you can load their page inside your own. That's what the attacker is doing here — loading the victim's **/my-account** page inside their fake exploit page.

---
### Frame-Busting Protections

Most secure websites **block** this behavior by using **security headers**. These headers tell the browser:

> “Hey, do NOT allow my site to be shown in an iframe on someone else's site.”

Here are the two main protections:

---

### 1. **`X-Frame-Options` Header**

This HTTP header prevents your site from being embedded in an iframe.

- `DENY` — No iframe embedding **allowed at all**.
- `SAMEORIGIN` — Only allow embedding **within your own site**.
    

> [!example]
> 
> `X-Frame-Options: DENY`
> 
> > This would completely block iframe loading, so the attacker can’t embed the page.
> 

---

### 2. **`Content-Security-Policy` (CSP) Header**

Another modern and powerful protection.

- **Directive:** `frame-ancestors`
- Controls **which sites** are allowed to embed your content.
    

> [!example]
> `Content-Security-Policy: frame-ancestors 'none';`
> 
> > This means **no site** (not even your own) can embed your content in an iframe.
> 

---

### ⚠️ Why This Lab Is Vulnerable

In the lab:

- The **/my-account** page does **NOT** set `X-Frame-Options` or CSP.
- So, the attacker is allowed to load `/my-account` inside an iframe.
- Then they **cover it up** with a fake-looking button using CSS.
- When the victim clicks the fake button, they’re **actually clicking** the real “Delete account” button underneath.


---
### ✅ Example of clickjacking leading to account takeover:

Suppose a vulnerable site has a "Change email" button, and **no CSRF protection**.  
The attacker builds an invisible iframe (like you did) over a "Click me" button.

When the victim clicks "Click me", they are **actually clicking "Change email"** on the real site — the attacker's email is already pre-filled because of crafted URL parameters or auto-filled fields.

Result:  
🔹 Victim unknowingly changes their account email to the attacker's email.  
🔹 Attacker then uses "Forgot Password" and resets the account access.  
🔹 **Account takeover successful!**

