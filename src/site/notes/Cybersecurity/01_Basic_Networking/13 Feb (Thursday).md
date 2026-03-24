---
{"dg-publish":true,"permalink":"/cybersecurity/01-basic-networking/13-feb-thursday/"}
---

 
threat vector, attack vector

## **Cybersecurity Essentials**

- **Cybersecurity**: The practice of protecting systems, networks, and data from cyber threats.
- **Threat Intelligence**: The process of collecting, analyzing, and sharing threat-related information to prevent cyberattacks.

---

### **Types of Threat Intelligence**

Threat Intelligence can be classified into four key categories based on its purpose, audience, and level of detail:

1. **Strategic Threat Intelligence**
2. **Tactical Threat Intelligence**
3. **Technical Threat Intelligence**
4. **Operational Threat Intelligence**

## **1. Strategic Threat Intelligence**

**Definition:**

- High-level intelligence that provides **big-picture insights** into the cybersecurity threat landscape.
- Helps **executives, decision-makers, and security leaders** understand potential threats and make informed business decisions.


**Purpose:**

- Focuses on **long-term trends, attack motivations, and geopolitical risks**.
- Aids in shaping an organization’s **security policies and investment strategies**.


**Key Characteristics:**  

- **Broad & High-Level:** Focuses on emerging threats, industry trends, and geopolitical risks.  
- **Long-Term Perspective:** Used for strategic planning rather than immediate action.  
- **Used by Decision-Makers:** Security executives, CISOs (Chief Information Security Officers), and risk analysts.


**Examples:**  

- Cyber threat reports from government agencies (e.g., NSA, CISA, Interpol).  
- Whitepapers on ransomware trends over the next five years.  
- Analysis of **nation-state cyber warfare threats**.  
- Reports on **AI-driven cyberattacks** and their potential future impact.


**How It's Used:**  

- Helps **justify cybersecurity budgets** to executives.  
- Guides **security investments** (e.g., should a company invest in AI-based threat detection?).  
- Shapes **cybersecurity regulations and policies** at national or organizational levels.


## **2. Tactical Threat Intelligence**

**Definition:**
- Provides **technical insights** into attack patterns, Tactics, Techniques, and Procedures (**TTPs**) used by cybercriminals.
- Helps **security teams** improve their defensive capabilities against known attack methods.

**Purpose:**
- Focuses on **how** attackers operate and how to defend against them.
- Used by **security teams** to strengthen security controls and develop effective countermeasures.

**Key Characteristics:**  
- **Focus on TTPs:** Analyzes attacker behaviors and methods.  
- **Used for Cyber Defense Planning:** Helps security teams configure firewalls, intrusion detection, and antivirus solutions.  
- **Bridges Strategy and Action:** Converts strategic intelligence into actionable insights.

**Examples:**  
- Analysis of how **APT groups** conduct attacks (e.g., how the Lazarus Group executes phishing campaigns).  
- MITRE ATT&CK framework data on attack patterns.  
- Studies on how malware spreads within a corporate network.  
- Identifying **security gaps in cloud environments**.

**How It's Used:**  
- Helps **SOC teams** fine-tune **firewall rules, SIEM alerts, and endpoint protection**.  
- Enables **penetration testers** to simulate attacks based on real-world threats.  
- Used by **cybersecurity architects** to design **resilient network infrastructure**.


## **3. Technical Threat Intelligence**

**Definition:**
- Focuses on **specific indicators of compromise (IoCs)** such as malware signatures, command-and-control (C2) IPs, phishing domains, and exploit codes.
- Helps security tools detect and block known threats automatically.

**Purpose:**
- Provides real-time threat intelligence to **automated security systems** (firewalls, IDS/IPS, endpoint detection tools).
- Used for **automated threat detection and blocking**.

**Key Characteristics:**  
- **Highly Detailed & Machine-Readable:** Used by security tools for automatic blocking and alerts.  
- **Short-Term Focus:** Deals with immediate threats rather than long-term strategies.  
- **Constantly Updated:** New threat signatures are continuously added.

**Examples:**  
- **IP addresses of known phishing sites**.  
- **Hashes of malware samples** (e.g., MD5, SHA-256).  
- **YARA Rules** for identifying malicious software.  
- **Domains used by botnets for C2 communication**.

**How It's Used:**  
- **SIEM systems** use technical intelligence to trigger alerts on suspicious activity.  
- **Firewalls and IDS/IPS** block connections from known malicious IPs.  
- **Endpoint protection solutions (EDR/XDR)** detect and quarantine malware.



## **4. Operational Threat Intelligence**

**Definition:**
- Real-time intelligence that provides insights into **ongoing cyberattacks, active threats, and attacker motivations**.
- Used by **incident response (IR) teams** to detect, analyze, and mitigate cyber incidents.

**Purpose:**
- Focuses on **who is attacking, what methods they are using, and what their goals are**.
- Helps **respond to cyber incidents quickly** and minimize damage.

**Key Characteristics:**  
- **Real-Time & Dynamic:** Used for immediate response.  
- **Focuses on Attackers & Motivations:** Helps track cybercriminal groups and ongoing campaigns.  
- **Highly Actionable:** Used by SOC and incident response teams.

**Examples:**  
- **Live monitoring of ransomware attacks in progress**.  
- **Tracking cybercriminal forums and dark web marketplaces** for leaked credentials.  
- **Intelligence on new zero-day exploits being actively used**.  
- **Monitoring phishing campaigns targeting specific industries**.

**How It's Used:**  
- Helps **incident response teams** quickly identify and contain attacks.  
- Used by **law enforcement agencies** to track cybercriminal activities.  
- Helps organizations adjust their **security postures dynamically** based on real-world threats.


## **Comparison Table: Strategic vs. Tactical vs. Technical vs. Operational Threat Intelligence**

|Type|Purpose|Audience|Timeframe|Examples|
|---|---|---|---|---|
|**Strategic**|High-level analysis of cyber threats & trends|Executives, CISOs, policymakers|Long-term (months/years)|Nation-state cyber warfare, industry threat reports|
|**Tactical**|Attack patterns, TTPs, and security defenses|Security teams, SOC analysts|Mid-term (weeks/months)|MITRE ATT&CK analysis, malware behavior reports|
|**Technical**|Indicators of Compromise (IoCs)|Automated security tools (SIEM, EDR, IDS)|Short-term (days/weeks)|Malware hashes, phishing domain lists, botnet IPs|
|**Operational**|Real-time attack tracking|Incident response teams, SOC analysts|Immediate (minutes/hours)|Active ransomware attack alerts, dark web tracking|

---

## **Phases of a Cyber Attack**

Cyber attacks typically follow these **five phases**:

1. **Footprinting** – Gathering information about the target (e.g., scanning public databases, using Google Dorking).
2. **Scanning** – Identifying vulnerabilities using tools like **Nmap, Nessus, or Shodan**.
3. **Gaining Access** – Exploiting vulnerabilities using **malware, phishing, or brute-force attacks**.
4. **Maintaining Access** – Installing backdoors or rootkits to ensure **persistent access**.
5. **Covering Tracks** – Deleting logs and masking activities to **avoid detection**.

> [!example]
> 
> **Sony Pictures Hack (2014)** – A case study where North Korean hackers breached Sony’s systems, leaked confidential data, and destroyed files.
> 

---

## **Sources of Threat Intelligence**

Threat intelligence comes from various sources:

- **Open-Source Intelligence (OSINT)** – Publicly available sources (e.g., security blogs, threat reports).  
- **Closed-Source Intelligence** – Private intelligence feeds from cybersecurity firms.  
- **Internal Data** – Logs from firewalls, Intrusion Detection Systems (IDS), and Security Information and Event Management (SIEM) solutions.  
- **Dark Web Intelligence** – Monitoring underground hacker forums and marketplaces.


---


## **Impacts of a Cyber Attack**

Cyber attacks can have severe consequences:

- **Reputational Impact** – Loss of customer trust and brand damage.  
- **Operational Impact** – Disruptions to business operations (e.g., ransomware shutting down hospitals).  
- **Financial Impact** – Loss of revenue, regulatory fines, ransom payments.  
- **Legal Impact** – Lawsuits and compliance violations.


---


