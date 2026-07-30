# Day 22: Malware Analysis & Detection

## Introduction

Malware (Malicious Software) is any software designed to damage systems, steal information, disrupt operations, or gain unauthorized access. SOC Analysts analyze malware to detect, investigate, contain, and prevent cyber attacks.

---

# What is Malware?

Malware is software intentionally created to harm computers, networks, or users.

### Objectives of Malware

- Steal sensitive information
- Encrypt files for ransom
- Spy on users
- Disrupt business operations
- Gain unauthorized access
- Create botnets
- Maintain persistence

---

# Characteristics of Malware

- Malicious in nature
- Executes without user knowledge
- Can self-replicate
- Hides from security tools
- Connects to Command & Control (C2) servers
- Steals or encrypts data
- Persists after reboot

---

# Types of Malware

## 1. Virus
Attaches to legitimate files and spreads when the file is executed.

**Example:** CIH Virus

---

## 2. Worm
Self-replicates without user interaction and spreads across networks.

**Example:** Conficker

---

## 3. Trojan
Disguises itself as legitimate software.

**Example:** Zeus Trojan

---

## 4. Ransomware
Encrypts files and demands payment.

**Example:** WannaCry

---

## 5. Spyware
Secretly monitors user activity and steals information.

---

## 6. Adware
Displays unwanted advertisements.

---

## 7. Rootkit
Hides malicious processes and provides attackers with privileged access.

---

## 8. Keylogger
Records keystrokes to steal usernames and passwords.

---

# Malware Infection Methods

- Phishing Emails
- Malicious Attachments
- Drive-by Downloads
- USB Devices
- Pirated Software
- Fake Software Updates
- Exploiting Vulnerabilities
- Remote Access Exploits

---

# Malware Lifecycle

1. Delivery
2. Execution
3. Installation
4. Persistence
5. Command & Control (C2)
6. Actions on Objectives
7. Cleanup or Further Spread

---

# Indicators of Compromise (IOC)

IOCs are evidence that a system has been compromised.

### Examples

- Malicious IP Address
- Malicious Domain
- File Hash (MD5, SHA1, SHA256)
- Suspicious URL
- Registry Changes
- Unknown Processes
- Scheduled Tasks

---

# Fileless Malware

Fileless malware operates in memory without writing files to disk.

### Common Techniques

- PowerShell
- WMI
- Windows Registry
- Macros
- Living-off-the-Land Binaries (LOLBins)

### Why is it Dangerous?

- Difficult to detect
- Leaves minimal traces
- Bypasses traditional antivirus

---

# Malware Communication (C2)

After infection, malware communicates with a Command & Control server.

### Common Indicators

- DNS Tunneling
- HTTP/HTTPS Beaconing
- Unknown Outbound Connections
- Encrypted Traffic
- Regular Network Beacons

---

# Malware Detection Using Windows Logs

### Important Event IDs

| Event ID | Description |
|----------|-------------|
| 4688 | Process Creation |
| 4104 | PowerShell Script Execution |
| 7045 | Service Installed |
| 1116 | Malware Detected by Defender |
| 5156 | Network Connection Allowed |

---

# Malware Detection Using Linux Logs

Important logs:

- /var/log/auth.log
- /var/log/syslog
- /var/log/messages
- /var/log/cron
- ~/.bash_history

---

# Malware Analysis Tools

## VirusTotal

Purpose:
- Scan files, URLs, IPs, Domains
- Check file reputation
- IOC lookup

SOC Usage:
Verify suspicious file hashes.

---

## Hybrid Analysis

Purpose:
Dynamic malware sandbox analysis.

SOC Usage:
Observe malware behavior safely.

---

## ANY.RUN

Purpose:
Interactive malware sandbox.

SOC Usage:
Analyze malware execution, processes, registry changes, and network traffic.

---

## MalwareBazaar

Purpose:
Repository of malware samples.

SOC Usage:
Download malware samples for research and IOC extraction.

---

## AlienVault OTX

Purpose:
Community Threat Intelligence Platform.

SOC Usage:
Search malicious IPs, domains, hashes, and threat pulses.

---

# WannaCry Ransomware Case Study

## Overview

WannaCry was a ransomware attack that spread rapidly across the world in 2017.

### Exploited

SMBv1 vulnerability (EternalBlue).

### Impact

- Encrypted files
- Displayed ransom demand
- Affected hospitals, banks, and businesses worldwide

### Prevention

- Apply security patches
- Disable SMBv1
- Use antivirus
- Maintain backups
- Enable firewalls

---

# Malware Investigation Workflow

1. Receive Alert
2. Validate Alert
3. Identify Infected Host
4. Collect Evidence
5. Analyze Malware
6. Search IOCs
7. Contain the Host
8. Remove Malware
9. Recover Systems
10. Document Incident

---

# SOC Analyst Tips

- Never execute suspicious files on a production system.
- Use sandbox environments for malware analysis.
- Verify hashes using VirusTotal.
- Correlate IOCs with Threat Intelligence.
- Isolate infected systems immediately.
- Preserve evidence before remediation.

---

# Tools Used

- VirusTotal
- Hybrid Analysis
- ANY.RUN
- MalwareBazaar
- AlienVault OTX
- Windows Defender
- Sysmon
- Wireshark
- Wazuh
- Splunk