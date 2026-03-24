---
{"dg-publish":true,"permalink":"/cybersecurity/01-basic-networking/17-feb-monday/"}
---

## *Task* :
use the following two tools in kali linux:
- Cyber Insurance (read)
- theHarvester
- recon-ng
- Tor (install in your machine) and try to explore darkweb
- volatality framework (read)
- windows patch management (read)
- OpenVas : vulnerability scanning

---
# **Cyber Insurance**

- also known as **cyber liability insurance** 
- a policy
- help businesses and individuals protect themselves from financial losses resulting from cyberattacks, data breaches, and other digital threats.

### **Who Needs Cyber Insurance?**

- **Businesses Handling Sensitive Data** – Banks, healthcare providers, e-commerce companies, and SaaS providers.
- **Small and Medium Businesses (SMBs)** – Often targets of cyberattacks due to limited security resources.
- **Freelancers and Consultants** – If handling client data or working remotely, insurance can mitigate risks.

[Refer this site !](https://www.fortinet.com/resources/cyberglossary/cyber-insurance)
[Refer this site !](https://www.techtarget.com/searchsecurity/definition/cybersecurity-insurance-cybersecurity-liability-insurance)

### **Advantages of cyber insurance**

Cyber insurance provides several key advantages for businesses and individuals dealing with digital risks. Here are the main benefits:

#### **1. Financial Protection**

Cyber insurance helps cover the **financial losses** resulting from cyberattacks, such as data breaches, ransomware, and business interruptions. Without coverage, companies may struggle to recover from costly incidents.

#### **2. Business Continuity Support**

Many policies include **business interruption coverage**, reimbursing lost revenue if a cyberattack disrupts operations. This ensures financial stability while systems are restored.

#### **3. Legal and Regulatory Compliance**

Cyberattacks often lead to legal consequences. Insurance covers **legal fees, regulatory fines, and penalties** associated with non-compliance with data protection laws (e.g., GDPR, CCPA).

#### **4. Data Breach Response Assistance**

Most policies provide **incident response services**, including forensic investigations, customer notification, credit monitoring for affected users, and crisis management.

#### **5. Reputation Management**

A data breach can damage customer trust. Cyber insurance often covers **public relations and reputation management costs** to restore brand credibility.

#### **6. Protection Against Ransomware**

With the rise of ransomware attacks, cyber insurance can cover **ransom payments, negotiation costs, and system restoration expenses**, helping businesses recover quickly.

#### **7. Risk Management Support**

Many insurers offer **pre-attack risk assessments and cybersecurity training**, helping businesses strengthen their defenses against potential threats.

#### **8. Third-Party Liability Coverage**

If customer or partner data is compromised, insurance can cover **legal claims and settlements**, reducing financial risks from lawsuits.


---

# **TheHarvester**

TheHarvester is an essential **OSINT** (Open-Source Intelligence) tool that helps ethical hackers gather public information on a target before conducting penetration testing. Combining it with tools like **Shodan**, **Maltego**, and **Recon-ng** enhances your recon capabilities.


### **Using and Implementing TheHarvester in Kali Linux**

**TheHarvester** is a powerful open-source reconnaissance tool used to gather information about a target from public sources like search engines, social media, and online databases. It is commonly used in penetration testing and ethical hacking.

---

### **1. Installing TheHarvester (If Not Pre-Installed)**

By default, **TheHarvester** comes pre-installed in Kali Linux. To check if it's installed, run:

bash :
`theHarvester -h`

If it's not installed, install it using:

bash :
`sudo apt update sudo apt install theharvester`

Alternatively, you can clone it from GitHub:

bash :
`git clone https://github.com/laramies/theHarvester.git cd theHarvester pip3 install -r requirements.txt python3 theHarvester.py -h`

---

### **2. Basic Syntax**

TheHarvester's general syntax is:

bash :
`theHarvester -d <domain> -b <source>`

- **`-d`** → Domain name (target website)
- **`-b`** → Data source (search engines, databases, social media, etc.)

### **3. Example Commands**

#### **a. Gather Emails and Subdomains from Google**

bash :
`theHarvester -d example.com -b google`

#### **b. Gather Emails from LinkedIn (API Required)**

bash :
`theHarvester -d example.com -b linkedin`

#### **c. Search for Subdomains and Hosts via Bing**

bash :
`theHarvester -d example.com -b bing`

#### **d. Search Across Multiple Sources**

bash :
`theHarvester -d example.com -b google,bing,yahoo`

#### **e. Save Output to a File**

bash :
`theHarvester -d example.com -b google -f example_results.txt`

#### **f. Generate HTML Report**

bash :
`theHarvester -d example.com -b all -f report.html`

---

### **4. Available Data Sources (`-b` options)**

- `google` → Google search engine
- `bing` → Bing search engine
- `yahoo` → Yahoo search engine
- `linkedin` → LinkedIn (requires API)
- `twitter` → Twitter profiles
- `shodan` → Shodan IoT database
- `virustotal` → VirusTotal database
- `certspotter` → SSL/TLS certificate transparency logs
- `all` → Runs searches on all available sources

---

### **5. Automating Reconnaissance with TheHarvester**

You can create a **bash script** to automate information gathering:

bash
`#!/bin/bash domain="example.com" echo "Running TheHarvester for $domain" theHarvester -d $domain -b all -f $domain-harvest.txt echo "Results saved in $domain-harvest.txt"`

Save it as `recon.sh` and run:

bash
`chmod +x recon.sh ./recon.sh`

---

### **6. Using TheHarvester with Proxy**

To run the tool through a proxy:

bash
`theHarvester -d example.com -b google --proxy http://127.0.0.1:8080`

----
## **Example**
### **Understanding the Output of the Command**

bash
`theHarvester -d flipkart.com -b yahoo`

This command instructs **TheHarvester** to gather publicly available information related to **flipkart.com** from **Yahoo Search**.

---

## **Breakdown of the Command**

- `theHarvester` → The tool for reconnaissance
- `-d flipkart.com` → The target domain (Flipkart)
- `-b yahoo` → The source (Yahoo search engine)

This means **TheHarvester** will search Yahoo for:  
- **Emails** → Extracted email addresses associated with `flipkart.com`  
- **Subdomains** → Identifying related subdomains  
- **Hosts** → IP addresses of found subdomains  
- **Employee names (if available)**  
- **Possible open ports and services**

[Reference for using theHarvester](https://www.geeksforgeeks.org/python-theharvester-how-to-use-it/)
[Github repo](https://github.com/laramies/theHarvester)


---

# **Recon-ng**

- **Recon-ng** is a powerful open-source web reconnaissance tool 
- pre-installed in Kali Linux
- helps gather **subdomains, emails, contacts, and more** using various modules and APIs.

### *Basic Commands*

| Command            | Description                  |
| ------------------ | ---------------------------- |
| `help`             | Lists all available commands |
| `run` or `execute` | `run` or `execute`           |
| `exit`             | Exits Recon-ng               |

[Reference for using recon-ng ](https://www.geeksforgeeks.org/recon-ng-installation-on-kali-linux/)

---

### **Difference btw using theHarvester and recon-ng**
- **TheHarvester** is a quick, command-line tool for gathering emails, subdomains, and hosts from search engines and public sources.
- **Recon-ng**, on the other hand, is a more advanced, modular framework with database support, API integrations, and automation capabilities for large-scale OSINT.


---

# **Tor in kali linux**

Tor Browser is a ****free and open-source**** software widely used to protect the personal privacy of its users. The [Features of Tor](https://www.geeksforgeeks.org/tor-browser-a-complete-overview/#features-of-tor-browser) ****include**** anonymously browsing over the internet and protecting your online privacy. It even allows accessing a website that is not permissible in your country. Tor allows people to access the internet anonymously by routing traffic through a worldwide network of relay servers.


