---
{"dg-publish":true,"permalink":"/port-swigger/clickjacking/lab2-clickjacking-with-form-input-data-prefilled-from-a-url-parameter/"}
---


Date : 12 Mar, 2025

----

[ACCESS THE LAB](https://portswigger.net/academy/labs/launch/8a7ec1665250f513f8ab3c341f7fcef5402a497d59fa90e673bfd30cd47ff766?referrer=%2fweb-security%2fclickjacking%2flab-prefilled-form-input)

> [!summary]
> - You are targeting a **Clickjacking attack** where **you fool the victim into clicking** the **"Update email"** button on their account settings page.
> - The **email input field** is **pre-filled automatically** using a **URL parameter** like:
>     
>     `?email=hacker@evil.com`
>     
> - So when the victim clicks the button ("Update email") **without realizing**, their email address gets changed to an attacker-controlled email.
> - After that, **attacker can reset the password** and **take over the account**.

You can log in to your own account using the following credentials: `wiener:peter`

## Motive:

| Aspect            | Explanation                                                     |
| ----------------- | --------------------------------------------------------------- |
| **Vulnerability** | No proper CSRF protection combined with trust in URL parameters |
| **Goal**          | Change victim’s account email to attacker’s email               |
| **Final Impact**  | Account takeover (by password reset to attacker's email)        |


---

## Solution :

1. Log in to the account on the target website.
![attachments/Pasted image 20250427135922.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427135922.png)

2. Go to the exploit server and paste the following HTML template into the "Body" section:
    
    `<style> iframe { position:relative; width:$width_value; height: $height_value; opacity: $opacity; z-index: 2; } div { position:absolute; top:$top_value; left:$side_value; z-index: 1; } </style> <div>Test me</div> <iframe src="YOUR-LAB-ID.web-security-academy.net/my-account?email=hacker@attacker-website.com"></iframe>`

3. Make the following adjustments to the template:
    - Replace `YOUR-LAB-ID` with your unique lab ID so that the URL points to the target website's user account page, which contains the "Update email" form.
    - ![attachments/Pasted image 20250427140205.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427140205.png)
    - Substitute suitable pixel values for the `$height_value` and `$width_value` variables of the iframe (we suggest 700px and 500px respectively).
    - Substitute suitable pixel values for the `$top_value` and `$side_value` variables of the decoy web content so that the "Update email" button and the "Test me" decoy action align (we suggest 400px and 80px respectively).
    - Set the opacity value `$opacity` to ensure that the target iframe is transparent. Initially, use an opacity of 0.1 so that you can align the iframe actions and adjust the position values as necessary. For the submitted attack a value of 0.0001 will work.
4. Click **Store** and then **View exploit**.
5. Hover over "Test me" and ensure the cursor changes to a hand indicating that the div element is positioned correctly. If not, adjust the position of the div element by modifying the top and left properties of the style sheet.
![attachments/Pasted image 20250427140422.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427140422.png)
6. Once you have the div element lined up correctly, change "Test me" to "Click me" and click **Store**.
![attachments/Pasted image 20250427140535.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427140535.png)

7. Change the email address in your exploit so that it doesn't match your own.
![attachments/Pasted image 20250427140628.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427140628.png)
8. Deliver the exploit to the victim to solve the lab.
![attachments/Pasted image 20250427140709.png|600](/img/user/Port%20Swigger/Clickjacking/attachments/Pasted%20image%2020250427140709.png)

---

> [!info]
> Result:  
> 🎯 Your account's email address is now **deepsthehacker@gmail.com**.  
> ➡️ Attacker uses "Forgot Password" → Reset link goes to their email → **Account hacked.**


