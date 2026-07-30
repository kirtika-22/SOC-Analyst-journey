# Day 21: Detecting Common Attacks 

## Introduction

A Security Operations Center (SOC) Analyst continuously monitors security events to identify and respond to cyber attacks. Detecting attacks early reduces damage and helps organizations respond quickly.

---

# Common Cyber Attacks

The most common attacks detected by SOC analysts are:

1. Brute Force Attack
2. Phishing Attack
3. Malware Infection
4. Privilege Escalation
5. Lateral Movement
6. Data Exfiltration
7. Command and Control (C2)
8. Web Application Attacks

---

# 1. Brute Force Attack

## Definition

A brute force attack is an attack where the attacker repeatedly tries different username and password combinations until the correct credentials are found.

## Indicators

- Multiple failed login attempts
- Login attempts from one IP address
- Successful login after many failures
- Multiple account lockouts

## Windows Event IDs

- **4625** – Failed Login
- **4624** – Successful Login
- **4740** – Account Locked
- **4776** – Credential Validation

## Linux Logs

- `/var/log/auth.log`
- `/var/log/secure`

### Example

```
Failed password for admin from 192.168.1.10
```

## SOC Response

- Block attacker IP
- Disable compromised account
- Reset password
- Enable MFA

---

# 2. Phishing Detection

## Definition

Phishing is a social engineering attack where attackers trick users into revealing credentials or downloading malware.

## Indicators

- Suspicious email sender
- Fake login page
- Unknown attachments
- Suspicious hyperlinks
- Credential harvesting

## MITRE ATT&CK

T1566 – Phishing

## SOC Investigation

- Check sender reputation
- Analyze URLs
- Scan attachments
- Search VirusTotal
- Block malicious domain

---

# 3. Malware Infection Detection

## Definition

Malware is malicious software designed to damage or steal information.

## Indicators

- Unknown process execution
- High CPU usage
- Antivirus alerts
- New scheduled tasks
- Unexpected outbound traffic

## Windows Event IDs

- **4688** – Process Creation
- **4104** – PowerShell Script Logging
- **7045** – New Service Installed
- **1116** – Malware Detected
- **5156** – Network Connection

## Linux Indicators

- Unknown cron jobs
- Modified binaries
- Suspicious shell history

## SOC Investigation

- Collect file hash
- Check VirusTotal
- Analyze running processes
- Isolate infected host

---

# 4. Privilege Escalation

## Definition

Privilege escalation occurs when an attacker gains higher permissions than originally allowed.

## Indicators

- User added to Administrators group
- New admin account
- Sudo misuse
- Registry changes
- New services

## Windows Event IDs

- 4728
- 4732
- 4756
- 4672

## SOC Response

- Verify changes
- Remove unauthorized privileges
- Investigate attacker activity

---

# 5. Lateral Movement

## Definition

After compromising one system, attackers move to other systems inside the network.

## Techniques

- RDP
- SMB
- PsExec
- WMI
- PowerShell Remoting

## Indicators

- Multiple remote logins
- Unusual SMB traffic
- Authentication from multiple hosts

## Event IDs

- 4624
- 4648
- 5140

---

# 6. Data Exfiltration

## Definition

Attackers steal confidential data from an organization.

## Indicators

- Large outbound traffic
- Upload to cloud storage
- Encrypted outbound connections
- Unusual FTP activity

## Detection

- DLP alerts
- Firewall logs
- Proxy logs
- NetFlow analysis

---

# 7. Command and Control (C2)

## Definition

After infection, malware communicates with the attacker's server.

## Indicators

- Regular beaconing
- DNS tunneling
- HTTPS communication to unknown domains
- Connections on uncommon ports

## Detection Tools

- Wireshark
- Zeek
- NetFlow
- Firewall Logs

---

# 8. Web Application Attack Detection

## Common Attacks

- SQL Injection
- Cross-Site Scripting (XSS)
- Command Injection
- Directory Traversal

## Indicators

- Repeated HTTP 500 errors
- SQL keywords in URLs
- Suspicious POST requests
- Multiple failed requests

## Logs

- Apache Access Log
- Nginx Access Log
- IIS Logs
- WAF Logs

---

# Windows Event IDs for Detection

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Login |
| 4625 | Failed Login |
| 4688 | Process Creation |
| 4104 | PowerShell Logging |
| 7045 | Service Installed |
| 1116 | Malware Detection |
| 4740 | Account Locked |
| 5156 | Network Connection |

---

# Important Linux Logs

| Log | Purpose |
|------|---------|
| /var/log/auth.log | Authentication |
| /var/log/secure | Login Activity |
| /var/log/syslog | System Logs |
| /var/log/messages | System Events |
| /var/log/cron | Scheduled Jobs |
| ~/.bash_history | User Commands |

---

# MITRE ATT&CK Mapping

| Attack | MITRE Technique |
|---------|-----------------|
| Phishing | T1566 |
| PowerShell | T1059 |
| Credential Dumping | T1003 |
| Lateral Movement | T1021 |
| Command & Control | T1071 |
| Data Exfiltration | T1041 |

---

# SOC Investigation Workflow

1. Alert Generated
2. Validate Alert
3. Collect Evidence
4. Investigate Logs
5. Enrich with Threat Intelligence
6. Identify IOC
7. Contain Threat
8. Eradicate Malware
9. Recover Systems
10. Document Incident

---

# Tools Used

- Wireshark
- Zeek
- NetFlow
- VirusTotal
- Splunk
- Wazuh
- Microsoft Defender
- Sysmon