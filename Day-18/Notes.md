# 📅 Day 18 – Threat Intelligence Basics & Indicators of Compromise (IOC)

## What is Threat Intelligence (TI)?

Threat Intelligence is knowledge about cyber adversaries, their tactics, techniques, procedures (TTPs), infrastructure, and motives that helps organizations detect and respond to cyber threats.

It answers:
- Who is attacking?
- What are they doing?
- Why are they attacking?
- How should we defend?

SOC analysts use threat intelligence to add context to security alerts.

---

# Types of Threat Intelligence

## 1. Strategic Threat Intelligence
- High-level overview
- Long-term trends
- Used by executives and management

Example:
- Increase in ransomware attacks targeting healthcare.

---

## 2. Tactical Threat Intelligence
Focuses on attacker TTPs.

Framework:
- MITRE ATT&CK

Used for:
- Detection engineering
- Security monitoring

---

## 3. Operational Threat Intelligence
Provides information about active attack campaigns.

Contains:
- Malware families
- Threat actors
- Target sectors
- Campaign information

---

## 4. Technical Threat Intelligence
Contains technical indicators such as:
- IP addresses
- Domains
- URLs
- File hashes
- Email indicators

This is the type most commonly used by SOC Analysts.

---

# Threat Intelligence Lifecycle

1. Planning
   - Define intelligence requirements.

2. Collection
   - Gather data from:
     - OSINT
     - Security logs
     - Threat feeds

3. Processing
   - Normalize data
   - Remove duplicates

4. Analysis
   - Convert raw data into actionable intelligence.

5. Dissemination
   - Share intelligence with SOC teams.

6. Feedback
   - Improve future intelligence collection.

---

# Sources of Threat Intelligence

## Open Source (OSINT)

- VirusTotal
- AbuseIPDB
- Shodan
- AlienVault OTX

## Commercial Sources

- FireEye
- Recorded Future
- Mandiant

## Internal Sources

- Firewall logs
- DNS logs
- Proxy logs
- SIEM alerts
- Previous incidents

## Sharing Communities

- ISAC
- MISP

---

# Why SOC Analysts Need Threat Intelligence

Threat Intelligence helps analysts:

- Enrich alerts
- Verify suspicious IPs
- Detect malicious domains
- Identify attacker infrastructure
- Improve threat hunting
- Build detection rules
- Speed up incident response

---

# Indicator of Compromise (IOC)

An Indicator of Compromise is evidence suggesting that malicious activity has occurred on a system or network.

Examples:
- Malicious IP addresses
- Suspicious domains
- Registry modifications
- Malicious processes
- Email headers
- File hashes

---

# Practical IOC Types

## IP Address
Used to identify:
- C2 servers
- Botnets
- Malicious communication

Checked in:
- Firewall logs
- Proxy logs

---

## Domains & URLs

Used for:
- Phishing detection
- Malware downloads

Checked in:
- DNS logs
- Proxy logs

---

## File Hashes

Examples:
- MD5
- SHA1
- SHA256

Purpose:
- Detect known malware

---

## Email Indicators

Examples:
- Sender address
- Subject
- Headers

Used during phishing investigations.

---

## Registry Keys & Processes

Used to identify:
- Persistence
- Malware execution

---

# IOC Investigation Example

Alert:
Outbound connection detected to **185.220.100.254**

Investigation Steps:
1. Search IP in VirusTotal.
2. Check AbuseIPDB.
3. Review firewall logs.
4. Review DNS logs.
5. Identify affected hosts.
6. Confirm malicious activity.
7. Escalate incident.

---

# SOC Workflow Using Threat Intelligence

Alert Generated
↓

Collect IOC
↓

Check VirusTotal / AbuseIPDB / Shodan

↓

Verify Reputation

↓

Search Internal Logs

↓

Confirm or Reject Threat

↓

Document Findings

↓

Escalate if Required

---

# Assignment

Collect three IOCs from:
- AlienVault OTX
- AbuseIPDB
- ThreatFox

Verify them in VirusTotal.

Identify where these IOCs would appear in:
- Firewall logs
- DNS logs
- Proxy logs
- SIEM alerts

---

# Key Takeaways

- Threat Intelligence provides context.
- IOC is evidence of compromise.
- Technical Threat Intelligence is used daily in SOC.
- VirusTotal, AbuseIPDB, Shodan, and AlienVault OTX are essential SOC tools.
- Threat Intelligence turns raw data into actionable knowledge.