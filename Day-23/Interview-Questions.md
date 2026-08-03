# Day 26 - Interview Questions

## 1. What is phishing?
Phishing is a social engineering attack that tricks users into revealing sensitive information or installing malware.

---

## 2. What are the common types of phishing?
- Credential Phishing
- Spear Phishing
- Whaling
- Business Email Compromise (BEC)

---

## 3. What is an email header?
An email header contains routing information such as sender, receiver, mail servers, authentication results, and message path.

---

## 4. What are SPF, DKIM, and DMARC?

**SPF:** Verifies that the sending mail server is authorized.

**DKIM:** Verifies that the email content has not been modified.

**DMARC:** Uses SPF and DKIM results to decide whether to accept, quarantine, or reject emails.

---

## 5. What are Indicators of Compromise (IOCs)?
IOCs are artifacts that indicate malicious activity, such as:
- IP Addresses
- Domains
- URLs
- File Hashes
- Email Addresses

---

## 6. Which tools are used for phishing investigation?
- VirusTotal
- URLScan
- MXToolbox
- Any.Run
- AbuseIPDB
- Cisco Talos
- IBM X-Force Exchange
- CheckPhish

---

## 7. How do you investigate a phishing email?

1. Analyze the email header.
2. Check SPF, DKIM, and DMARC.
3. Extract IOCs.
4. Verify URLs, IPs, domains, and hashes.
5. Correlate logs in Splunk.
6. Prepare the investigation report.

---

## 8. Why is MITRE ATT&CK important?
It helps map attacker techniques and improves threat detection and incident response.

---

## 9. How does Splunk help in phishing analysis?
Splunk correlates email, DNS, proxy, and endpoint logs to identify compromised users and detect phishing campaigns.

---

## 10. What should a phishing investigation report include?
- Executive Summary
- Email Metadata
- IOC Table
- Findings
- MITRE Mapping
- Recommendations

---

## 11. How can organizations prevent phishing?
- Enable SPF, DKIM, and DMARC
- Use Email Sandboxing
- Conduct Security Awareness Training
- Whitelist trusted domains
- Update Threat Intelligence feeds

---

## 12. What is the role of a SOC Analyst during a phishing incident?
A SOC Analyst investigates suspicious emails, validates IOCs, correlates logs, identifies affected users, contains the threat, and documents the incident.