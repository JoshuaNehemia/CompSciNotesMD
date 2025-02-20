# Introduction to Security Operations Center (SOC)  

## SOC Definition  
The **Security Operations Center (SOC)** is the first line of defense against IT security breaches. It continuously monitors, detects, and responds to cybersecurity threats.  

### SOC Analyst Tiers  
SOC operates in multiple **tiers**, each with specific responsibilities:  

- **Tier 1 – Triage Specialist**  
  - Analyzes alerts to determine if they are **justified threats** or **false positives**.  
  - If justified, escalates the issue to **Tier 2**.  

- **Tier 2 – Incident Handler**  
  - Conducts an **in-depth assessment** using security toolkits.  
  - Identifies the **scope of the attack** and determines affected systems.  
  - If the attack involves a **zero-day vulnerability**, escalates it to **Tier 3**.  

> **Nice to Know**  
> **Zero-Day Attack**: A cyberattack that exploits a software vulnerability **before a fix is available**.  
> - Since no patch exists, conventional security toolkits may be ineffective.  
> - Requires **advanced threat-hunting techniques** to mitigate.  

- **Tier 3 – Threat Hunter (Incident Responder)**  
  - Focuses on proactive **threat detection**.  
  - Investigates advanced and persistent threats.  
  - Responds to complex cyberattacks.  

### SOC Leadership Roles  
- **SOC Manager**  
  - Leads the SOC team and provides **technical guidance**.  

- **Chief Information Security Officer (CISO)**  
  - The SOC Manager reports to the **CISO**.  
  - Defines **security strategies, goals, and objectives** for the organization.  

## Security Teams & Key Roles  

### **Red Team vs. Blue Team**  
- **Red Team**: Simulates **attacks** to find vulnerabilities.  
- **Blue Team**: Defends against attacks and strengthens security.  

### **Security Engineer**  
- Develops, maintains, and integrates **SOC tools**.  
- Ensures the effectiveness of security infrastructure.  

### **SOC’s Role in Cybersecurity**  
- Serves as the **first line of defense** against cybersecurity threats.  
- Works proactively to **contain and neutralize threats**.  

---

## SOC Environment  

### **Primary Goal: Minimize Dwell Time**  
> **Dwell Time**: The total time an attacker remains inside a system before detection.  
> - A lower dwell time means **faster threat detection and response**.  
> - Organizations measure dwell time to **assess security effectiveness**.  
> - Drills and simulations help SOC teams **improve response times**.  

### **Understanding Threat Actors**  
Cybercriminals have different motives for launching attacks:  

#### **Primary Motive: Financial Gain**  
- Ransomware attacks  
- Data theft for sale on the black market  

#### **Secondary Motive: Espionage (Spying)**  
- Corporate espionage  
- Government intelligence gathering  
- Clandestine motives (stealth operations)  

### **Common Attack Methods**  

#### **1. Phishing**  
- A **social engineering attack** where attackers trick individuals into providing sensitive information.  
- Often involves fake emails, messages, or websites that appear legitimate.  

#### **2. Ransomware**  
- Usually delivered via **phishing emails**.  
- Attackers encrypt the target's **hard drive** and demand a ransom to unlock it.  
- May also **threaten to publish stolen data** if the ransom is not paid.  

### **Threat Actors & Social Engineering**  
- Threat actors **spy** on individuals and organizations to gather information.  
- They **customize phishing attacks** based on collected details.  
- **Not just generic spam** – attacks can look like **legitimate company emails**.  
- This tactic is known as **social engineering**.  

---

## Incident Response  

### **Collecting Evidence & IT Forensics**  
- **Incident response teams** gather **artifacts** (evidence) from an attack.  
- This data is analyzed for **forensic investigations** and recovery processes.  

### **SOC Procedures & Standards**  
SOC follows **multiple standardized procedures** to ensure efficient security operations.  

Example: **ACME Inc. SOC Policies & Best Practices**  

## Goal of SOC



## Challenges of a SOC