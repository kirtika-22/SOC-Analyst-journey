# Day 22 - Malware Analysis & Detection - Interview Questions

## 1. What is Malware?

**Answer:**
Malware (Malicious Software) is software designed to damage systems, steal information, disrupt operations, or gain unauthorized access.

Examples:
- Virus
- Worm
- Trojan
- Ransomware
- Spyware
- Rootkit

---

## 2. What are the objectives of Malware?

**Answer:**
- Steal sensitive information
- Encrypt files for ransom
- Spy on users
- Gain unauthorized access
- Disrupt business operations
- Create botnets
- Maintain persistence

---

## 3. What is the difference between a Virus and a Worm?

**Answer:**

| Virus | Worm |
|--------|------|
| Requires user action | Self-replicates automatically |
| Attaches to files | Independent malware |
| Slower spread | Faster spread across networks |

---

## 4. What is a Trojan?

**Answer:**
A Trojan is malware that disguises itself as legitimate software to trick users into installing it.

**Example:** Zeus Trojan

---

## 5. What is Ransomware?

**Answer:**
Ransomware encrypts a victim's files and demands payment for the decryption key.

**Example:** WannaCry

---

## 6. What is Spyware?

**Answer:**
Spyware secretly monitors user activities and steals sensitive information such as passwords, browsing history, and banking details.

---

## 7. What is a Rootkit?

**Answer:**
A Rootkit is malware that hides malicious processes and provides attackers with privileged access while avoiding detection.

---

## 8. What is Fileless Malware?

**Answer:**
Fileless malware runs in memory without writing files to disk, making it difficult for traditional antivirus software to detect.

**Common Techniques:**
- PowerShell
- WMI
- Windows Registry
- LOLBins

---

## 9. What are Indicators of Compromise (IOCs)?

**Answer:**
IOCs are evidence that a system has been compromised.

**Examples:**
- Malicious IP
- Domain
- File Hash
- URL
- Registry Change
- Suspicious Process

---

## 10. What is Command and Control (C2)?

**Answer:**
Command and Control (C2) is the communication channel between malware and the attacker's server, allowing attackers to send commands and receive stolen data.

---

## 11. What are common malware infection methods?

**Answer:**
- Phishing emails
- Malicious attachments
- Drive-by downloads
- USB devices
- Pirated software
- Fake updates
- Exploiting vulnerabilities

---

## 12. Explain the Malware Lifecycle.

**Answer:**
1. Delivery
2. Execution
3. Installation
4. Persistence
5. Command & Control (C2)
6. Actions on Objectives
7. Cleanup or Further Spread

---

## 13. How do SOC Analysts detect malware?

**Answer:**
SOC Analysts use:
- SIEM alerts
- Windows Event Logs
- Linux Logs
- Antivirus alerts
- EDR tools
- Network traffic analysis
- Threat Intelligence platforms

---

## 14. Which Windows Event IDs are important for malware detection?

**Answer:**

| Event ID | Description |
|----------|-------------|
| 4688 | Process Creation |
| 4104 | PowerShell Script Execution |
| 7045 | Service Installation |
| 1116 | Microsoft Defender Malware Detection |
| 5156 | Network Connection |

---

## 15. Which Linux logs help detect malware?

**Answer:**
- `/var/log/auth.log`
- `/var/log/syslog`
- `/var/log/messages`
- `/var/log/cron`
- `~/.bash_history`

---

## 16. What is VirusTotal?

**Answer:**
VirusTotal is an online malware analysis platform used to scan files, URLs, IP addresses, domains, and hashes using multiple antivirus engines.

---

## 17. What is Hybrid Analysis?

**Answer:**
Hybrid Analysis is a malware sandbox that performs dynamic analysis to observe malware behavior in a secure environment.

---

## 18. What is ANY.RUN?

**Answer:**
ANY.RUN is an interactive malware sandbox that allows analysts to safely execute malware and monitor processes, registry changes, file activity, and network communication.

---

## 19. What is MalwareBazaar?

**Answer:**
MalwareBazaar is a repository of malware samples used by security researchers and SOC analysts for malware research and IOC extraction.

---

## 20. What is AlienVault OTX?

**Answer:**
AlienVault Open Threat Exchange (OTX) is a community-driven Threat Intelligence platform used to search malicious IPs, domains, hashes, URLs, and threat pulses.

---

## 21. Explain the WannaCry attack.

**Answer:**
WannaCry was a ransomware attack in 2017 that exploited the SMBv1 vulnerability (EternalBlue). It spread rapidly, encrypted files, and demanded ransom from victims.

---

## 22. How would you investigate a malware alert as a SOC Analyst?

**Answer:**
1. Validate the alert.
2. Identify the affected host.
3. Collect logs and evidence.
4. Analyze processes and network activity.
5. Check file hash in VirusTotal.
6. Search IOCs in Threat Intelligence platforms.
7. Isolate the infected host.
8. Remove malware.
9. Recover the system.
10. Document the incident.

---

## 23. Which tools are commonly used for malware analysis?

**Answer:**
- VirusTotal
- Hybrid Analysis
- ANY.RUN
- MalwareBazaar
- AlienVault OTX
- Wireshark
- Sysmon
- Splunk
- Wazuh

---

## 24. Difference between Static Analysis and Dynamic Analysis?

| Static Analysis | Dynamic Analysis |
|-----------------|------------------|
| Examines malware without running it | Executes malware in a sandbox |
| Faster | More detailed |
| Lower risk | Reveals real behavior |

---

## 25. Quick Revision

- Malware = Malicious Software
- Virus → Needs Host File
- Worm → Self-Replicates
- Trojan → Disguised as Legitimate Software
- Ransomware → Encrypts Files
- Spyware → Steals Information
- Rootkit → Hides Malware
- IOC → Evidence of Compromise
- C2 → Malware Communication
- VirusTotal → File/Hash Analysis
- Hybrid Analysis → Dynamic Malware Analysis
- ANY.RUN → Interactive Sandbox
- MalwareBazaar → Malware Sample Repository
- AlienVault OTX → Threat Intelligence Platform
- WannaCry → SMBv1 (EternalBlue) Ransomware