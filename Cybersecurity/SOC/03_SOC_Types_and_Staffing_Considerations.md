# SOC Types and Staffing Considerations

## SOC Objective
- **Monitor**
- **Detect**
- **Investigate**
- **Respond**
- **Contain**

A SOC monitors and analyzes suspicious activity to protect an organization's security.

## Various SOC Types
Organizations have different security requirements, and SOCs are designed to address these needs in different ways.

### 1. Threat-Centric SOC
A **Threat-Centric SOC** proactively hunts for malicious threats in an organization's network, profiles attackers, and identifies potential threats.

#### Activities:
- **Threat Hunting:**
  - Searches for attackers operating under the radar or through attack vectors.
> An **attack vector** is the method or path an attacker uses to breach an organization's security. Common attack vectors include:
> - **Phishing:** Deceptive emails or messages tricking users into revealing credentials.
> - **Malware:** Malicious software like ransomware or spyware.
> - **Exploiting Vulnerabilities:** Attacking unpatched software or misconfigured systems.
> - **Insider Threats:** Employees or contractors intentionally or unintentionally causing security breaches.
> - **Social Engineering:** Manipulating people into disclosing confidential information.

  - Attackers only succeed when vulnerabilities are present.
  - Requires **threat intelligence** to seek out Indicators of Compromise (IoCs).
- **Threat Modeling:**
  - Identifies and assesses potential threats.
  - Determines organizational vulnerabilities and relevant threats.
  - Helps the SOC safeguard against threats and threat actors.
- **Tracking Threat Actors:**
  - **Steps in Threat Modeling:**
    1. Identify assets that need protection.
    2. Prioritize assets based on vulnerability and attack vectors.
    3. Develop a **system abstract** profiling adversaries, their capabilities, goals, methods, and motivations.
    4. Track threat actors and analyze their Tactics, Techniques, and Procedures (TTPs).
  - Associates observed behaviors with known threat actors.
  - Enhances attack response efficiency.

**Example:**
Kathy, a SOC analyst, uses **Cisco Talos threat intelligence** and other sources to perform proactive threat hunting. Her vigilance helped prevent a major ransomware attack. She continuously questions potential threats and how they might unfold.

---

### 2. Compliance-Based SOC
A **Compliance-Based SOC** focuses on adhering to compliance policies and regulatory requirements.

#### Key Considerations:
- Ensures the organization meets compliance mandates.
- Tracks necessary procedures for **proving and reporting compliance**.

**Example:**
A large bookstore chain operates exclusively online, accepting only **credit card payments**. By law, they must comply with **PCI DSS (Payment Card Industry Data Security Standard)**. Their SOC implements:
- **Encryption protocols**
- **Password policies**
- **Firewall configurations**
- Incident management based on **PCI DSS guidelines**

---

### 3. Operational-Based SOC
An **Operational-Based SOC** focuses on the organization's internal security posture, aiming to protect critical assets and ensure rapid threat containment, eradication, and recovery.

#### Key Questions:
- **What should we be protecting?**
- **How should we protect it?**

**Example:**
A **municipality registering motor vehicles** considers **driver’s license information** a critical asset. Their SOC:
- Secures **identity management systems**.
- Develops **mitigation actions** for incidents like identity theft.
- Creates and distributes **zero-day attack signatures** to security infrastructure (e.g., firewalls, IDS/IPS systems).

This SOC type is also known as a **Computer Security Incident Response Team (CSIRT).**

---

## Conclusion
Organizations may incorporate multiple SOC types to meet their security requirements. Understanding SOC types helps in selecting the right model for an organization and aligning security strategies accordingly.
