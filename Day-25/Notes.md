# Day 25 - Alert Triage & SOC Alert Handling

## What is Alert Triage?

Alert triage is the process of reviewing, validating, prioritizing, and investigating security alerts to determine whether they represent a real security incident.

The goal of alert triage is to quickly distinguish between True Positives and False Positives while ensuring critical incidents receive immediate attention.

---

# Objectives of Alert Triage

- Identify real threats quickly
- Eliminate false positives
- Prioritize alerts based on severity
- Reduce analyst workload
- Improve incident response efficiency

---

# Why Alert Triage is Important

SOC teams receive thousands of alerts every day.

Without alert triage:
- Analysts waste time investigating false positives.
- Critical attacks may be missed.
- Incident response becomes slow.
- Alert fatigue increases.

Benefits:
- Reduces alert fatigue
- Improves SOC efficiency
- Ensures high-risk incidents receive immediate attention
- Provides better investigation context
- Speeds up incident response

---

# Types of Security Alerts

## 1. Authentication Alerts

Examples:
- Failed logins
- Brute-force attacks
- Account lockouts
- Privilege escalation

Sources:
- Windows Event Logs
- Active Directory
- Wazuh
- Microsoft Defender

---

## 2. Network Alerts

Examples:
- Suspicious outbound traffic
- Port scanning
- Network intrusion
- DNS anomalies

Sources:
- Firewall
- IDS/IPS
- Proxy Logs
- Network Monitoring Tools

---

## 3. Endpoint Alerts

Examples:
- Malware execution
- Suspicious PowerShell
- Unauthorized software
- Ransomware behavior

Sources:
- Wazuh
- Sysmon
- EDR
- Antivirus

---

## 4. Email Alerts

Examples:
- Phishing emails
- Malicious attachments
- Suspicious URLs
- Email spoofing

Sources:
- Email Security Gateway
- Microsoft Defender for Office 365

---

## 5. Cloud Alerts

Examples:
- Suspicious IAM activity
- Impossible travel
- New admin account
- Public storage bucket

Sources:
- AWS CloudTrail
- Azure Logs
- GCP Logs

---

# SOC Alert Flow

Security Event

↓

Log Generated

↓

Collected by SIEM (Wazuh)

↓

Detection Rule Matches

↓

Alert Generated

↓

SOC L1 Receives Alert

↓

Alert Triage

↓

True Positive?

├── No → Close Ticket

└── Yes

↓

Incident Created

↓

Escalate to L2/L3

↓

Incident Response

---

# Five-Step Alert Triage Process

## Step 1 - Identify Alert Context

Understand the alert before investigating.

Questions to ask:
- Which device generated the alert?
- Which user is involved?
- What is the hostname?
- What time did it occur?
- Which rule triggered?
- What is the severity?
- Which asset is affected?

---

## Step 2 - Gather Evidence

Collect all relevant evidence.

Evidence Sources:
- Wazuh SIEM Logs
- Windows Event Logs
- Sysmon Logs
- EDR Logs
- Firewall Logs
- Proxy Logs
- Active Directory
- Threat Intelligence
- User Information
- Asset Inventory

---

## Step 3 - Validate the Alert

Determine whether the alert is legitimate.

Possible Results:

### True Positive

A real security incident.

Example:
Malware execution confirmed on a workstation.

### False Positive

Benign activity incorrectly detected.

Example:
User mistyped password several times.

---

## Step 4 - Determine Severity

Severity depends on:

- Business Impact
- Asset Criticality
- Scope
- Threat Type
- Confidence Level

Severity Levels:

- Informational
- Low
- Medium
- High
- Critical

---

## Step 5 - Escalate or Close

If True Positive:
- Create Incident Ticket
- Document Evidence
- Escalate to L2/L3

If False Positive:
- Document Findings
- Close Ticket

---

# Tools Used During Alert Triage

## SIEM
- Wazuh
- Splunk
- Microsoft Sentinel

Purpose:
Collect and correlate security logs.

---

## Endpoint Detection & Response (EDR)

Examples:
- Microsoft Defender
- CrowdStrike
- SentinelOne

Purpose:
Investigate endpoint activity.

---

## Threat Intelligence

Examples:
- VirusTotal
- AlienVault OTX
- MISP

Purpose:
Validate IPs, domains, URLs, and file hashes.

---

## Firewall

Examples:
- Palo Alto
- Fortinet
- Cisco ASA

Purpose:
Investigate network traffic.

---

## Active Directory

Purpose:
Verify user accounts and group memberships.

---

## Ticketing Platforms

Examples:
- TheHive
- ServiceNow
- Jira

Purpose:
Track investigations and incidents.

---

# Best Practices for Alert Triage

- Investigate before escalating.
- Never assume every alert is malicious.
- Correlate multiple logs.
- Check threat intelligence before making decisions.
- Follow the organization's playbooks.
- Document every investigation.
- Prioritize critical assets.
- Escalate only with sufficient evidence.
- Maintain accurate timelines.
- Communicate clearly with L2/L3 teams.