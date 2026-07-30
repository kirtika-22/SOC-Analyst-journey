# Day 21 Interview Questions & Answers

## 1. What is a Brute Force Attack?

**Answer:**
A Brute Force Attack is a password attack where an attacker repeatedly tries different username and password combinations until the correct credentials are found.

---

## 2. How can a SOC Analyst detect a Brute Force Attack?

**Answer:**
A SOC Analyst detects it by monitoring:
- Multiple failed login attempts (Windows Event ID 4625)
- Successful login after multiple failures (Event ID 4624)
- Repeated login attempts from the same IP address
- Account lockouts (Event ID 4740)
- Linux authentication logs (`/var/log/auth.log` or `/var/log/secure`)

---

## 3. What is Phishing?

**Answer:**
Phishing is a social engineering attack where attackers trick users into revealing sensitive information such as usernames, passwords, or banking details through fake emails, websites, or messages.

---

## 4. How do you investigate a phishing email?

**Answer:**
1. Check sender email address.
2. Analyze embedded URLs.
3. Scan attachments using VirusTotal.
4. Verify domain reputation.
5. Search IOCs in Threat Intelligence platforms.
6. Block malicious domains and notify users.

---

## 5. What is Malware?

**Answer:**
Malware is malicious software designed to damage systems, steal data, spy on users, or gain unauthorized access.

Examples:
- Virus
- Worm
- Trojan
- Ransomware
- Spyware
- Rootkit

---

## 6. How can you detect Malware?

**Answer:**
Indicators include:
- Unknown processes
- Antivirus alerts
- High CPU or memory usage
- Suspicious PowerShell execution
- Unexpected outbound network connections
- Unknown scheduled tasks
- File hash matching known malware

---

## 7. Which Windows Event IDs are important for malware detection?

**Answer:**

| Event ID | Description |
|----------|-------------|
| 4688 | Process Creation |
| 4104 | PowerShell Script Logging |
| 7045 | Service Installation |
| 1116 | Microsoft Defender Malware Detection |
| 5156 | Windows Filtering Platform Network Connection |

---

## 8. What is Privilege Escalation?

**Answer:**
Privilege Escalation is a technique where an attacker gains higher permissions than originally assigned, such as obtaining Administrator or Root privileges.

---

## 9. What are indicators of Privilege Escalation?

**Answer:**
- New administrator account
- User added to Administrators group
- Sudo abuse
- Service installation
- Registry modifications
- Security policy changes

---

## 10. What is Lateral Movement?

**Answer:**
Lateral Movement is the technique attackers use to move from one compromised system to another inside the same network.

---

## 11. Which protocols are commonly used for Lateral Movement?

**Answer:**
- RDP
- SMB
- WinRM
- WMI
- PsExec
- SSH

---

## 12. What is Data Exfiltration?

**Answer:**
Data Exfiltration is the unauthorized transfer of sensitive data from an organization's network to an external destination.

---

## 13. What are indicators of Data Exfiltration?

**Answer:**
- Large outbound traffic
- Uploads to cloud storage
- Unknown FTP connections
- Encrypted outbound communication
- Unusual DNS requests

---

## 14. What is Command and Control (C2)?

**Answer:**
Command and Control (C2) is the communication channel between infected systems and the attacker's server used to send commands and receive stolen data.

---

## 15. How do SOC Analysts detect C2 communication?

**Answer:**
- Regular beaconing traffic
- DNS tunneling
- Connections to malicious IPs or domains
- HTTPS traffic to unknown destinations
- Unusual outbound ports

---

## 16. What are Web Application Attacks?

**Answer:**
Web Application Attacks target websites or web applications to exploit vulnerabilities.

Common examples:
- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- Directory Traversal
- File Inclusion

---

## 17. Which Windows Event IDs should every SOC Analyst remember?

**Answer:**

- 4624 – Successful Logon
- 4625 – Failed Logon
- 4688 – Process Creation
- 4104 – PowerShell Logging
- 7045 – Service Installation
- 1116 – Malware Detection
- 4740 – Account Lockout
- 5156 – Network Connection

---

## 18. Which Linux logs are commonly investigated?

**Answer:**
- `/var/log/auth.log`
- `/var/log/secure`
- `/var/log/syslog`
- `/var/log/messages`
- `/var/log/cron`
- `~/.bash_history`

---

## 19. What is MITRE ATT&CK?

**Answer:**
MITRE ATT&CK is a knowledge base that maps attacker Tactics, Techniques, and Procedures (TTPs). It helps SOC Analysts understand, detect, and respond to cyber attacks.

---

## 20. Explain the SOC Investigation Workflow.

**Answer:**
1. Alert Generation
2. Alert Validation
3. Evidence Collection
4. Log Analysis
5. Threat Intelligence Enrichment
6. IOC Identification
7. Containment
8. Eradication
9. Recovery
10. Documentation

---

# HR + Technical Interview Questions

### Q1. What would you do if you receive multiple failed login alerts?

**Answer:**
I would verify the source IP, review Event ID 4625 logs, correlate with successful logins (4624), check for account lockouts, determine if it is a brute-force attack, and take containment actions such as blocking the IP or disabling the account if required.

---

### Q2. Which logs do you check first during an investigation?

**Answer:**
- Windows Security Logs
- Sysmon Logs
- Microsoft Defender Logs
- Firewall Logs
- Proxy Logs
- Linux Authentication Logs
- SIEM Alerts

---

### Q3. Which tools have you used for attack detection?

**Answer:**
- Wazuh
- Splunk
- Wireshark
- Zeek
- VirusTotal
- Microsoft Defender
- NetFlow
- Sysmon

---

### Q4. What is the difference between IOC and IOA?

**Answer:**
- **IOC (Indicator of Compromise):** Evidence that a system has already been compromised (e.g., malicious IP, hash, domain).
- **IOA (Indicator of Attack):** Suspicious behavior indicating an attack may be in progress (e.g., repeated failed logins, PowerShell abuse).

---

### Q5. As a fresher, how would you investigate a malware alert?

**Answer:**
I would validate the alert, collect logs, identify the affected host, check the file hash in VirusTotal, review process creation events, analyze network connections, isolate the system if necessary, and document the findings.
