# Day 26 - Phishing Email Analysis

# What is Phishing?

Phishing is a social engineering attack that tricks users into revealing sensitive information, clicking malicious links, or downloading malware.

---

# Common Types

- Credential Phishing
- Malware Delivery
- Business Email Compromise (BEC)
- Spear Phishing
- Whaling

---

# Email Header Analysis

Important fields:
- Return-Path
- Received
- Message-ID
- Reply-To
- From
- SPF/DKIM/DMARC Results

---

# Email Authentication

## SPF
Validates the sender's mail server.

## DKIM
Verifies email integrity.

## DMARC
Uses SPF and DKIM to decide whether to accept, reject, or quarantine emails.

---

# Indicators of Compromise (IOCs)

- Malicious URLs
- Sender Domain
- Source IP Address
- File Hashes
- Attachments

---

# IOC Analysis Tools

## URL Analysis
- URLScan
- VirusTotal
- IPinfo
- CheckPhish

## File & Malware Analysis
- Any.Run
- FileScan
- Cuckoo Sandbox
- VMware Sandbox

## Email Header Analysis
- MXToolbox
- Google Message Header
- Azure Header Analyzer
- MailHeader
- GoJinx Header Analyzer

## Threat Intelligence
- AbuseIPDB
- IBM X-Force Exchange
- Cisco Talos
- URLScan
- VirusTotal

---

# Phishing Investigation Steps

1. Collect the suspicious email.
2. Analyze email headers.
3. Verify SPF, DKIM, and DMARC.
4. Extract IOCs.
5. Check URLs, domains, IPs, and hashes.
6. Correlate logs in SIEM.
7. Confirm phishing activity.
8. Create an investigation report.

---

# MITRE ATT&CK Mapping

| Technique | ATT&CK ID |
|-----------|-----------|
| Phishing | T1566 |
| User Execution | T1204 |
| Credential Phishing | T1566.002 |
| Email Collection | T1114 |
| Exfiltration Over Web | T1567 |

---

# Splunk Use Case

- Search email logs.
- Correlate DNS and proxy logs.
- Identify users who clicked malicious links.
- Detect repeated phishing attempts.

---

# Reporting

A phishing report should include:
- Executive Summary
- Email Metadata
- IOC List
- Findings
- MITRE Mapping
- Recommendations

---

# Prevention

- Enable SPF, DKIM & DMARC
- Email Sandboxing
- Domain Whitelisting
- User Awareness Training
- Update Threat Intelligence Feeds