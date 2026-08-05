# Day 24 Interview Questions

## 1. What is Incident Response?

Incident Response is a structured process used to detect, analyze, contain, eradicate, recover, and learn from cybersecurity incidents while minimizing business impact.

---

## 2. What are the six phases of Incident Response?

1. Preparation
2. Detection & Analysis
3. Containment
4. Eradication
5. Recovery
6. Post-Incident Review

---

## 3. What are the responsibilities of an L1 SOC Analyst?

- Monitor alerts
- Perform alert triage
- Validate alerts
- Gather evidence
- Classify incidents
- Create tickets
- Escalate incidents
- Document findings

---

## 4. What is Alert Triage?

Alert triage is the process of reviewing, validating, and prioritizing security alerts to determine whether they represent a real security incident.

---

## 5. What is the difference between an Event, Alert, and Incident?

**Event**
A single activity recorded in logs.

**Alert**
A notification generated when detection rules are triggered.

**Incident**
A confirmed security event that requires response.

---

## 6. What is a True Positive?

A legitimate security incident correctly detected by the security tool.

Example:
Malware execution detected by Wazuh.

---

## 7. What is a False Positive?

A legitimate activity incorrectly identified as malicious.

Example:
Employee enters an incorrect password several times.

---

## 8. What information do you collect during an investigation?

- Hostname
- Username
- Source IP
- Destination IP
- Timestamp
- Detection rule
- Severity
- Related logs
- Threat Intelligence results

---

## 9. What are common evidence sources?

- Wazuh SIEM logs
- Windows Event Logs
- Sysmon
- Firewall Logs
- EDR
- VirusTotal
- AlienVault OTX

---

## 10. What is Containment?

Containment prevents an attack from spreading.

Examples:
- Disable user account
- Isolate endpoint
- Block malicious IP
- Block malicious domain

---

## 11. What is Eradication?

Eradication removes the attacker completely.

Examples:
- Delete malware
- Remove persistence
- Patch vulnerabilities
- Reset passwords

---

## 12. What is Recovery?

Recovery restores systems to normal operation while ensuring they are clean and secure.

---

## 13. What is Root Cause Analysis (RCA)?

Root Cause Analysis identifies how the incident occurred and helps prevent similar attacks.

---

## 14. Why is documentation important?

Documentation:
- Supports investigations
- Provides audit evidence
- Helps future analysts
- Improves incident response

---

## 15. What tools are commonly used in Incident Response?

- Wazuh
- Splunk
- Microsoft Sentinel
- Microsoft Defender
- CrowdStrike
- VirusTotal
- AlienVault OTX
- MISP
- TheHive
- ServiceNow

---

# Scenario-Based Questions

## Q1

Wazuh detects multiple failed login attempts followed by a successful login from a foreign IP. What would you do?

Answer:
- Review the alert
- Verify affected user and host
- Collect related logs
- Check source IP using Threat Intelligence
- Determine if it is a true positive
- Create an incident ticket
- Escalate to L2
- Document all findings

---

## Q2

What do you do if the alert is a false positive?

Answer:
- Verify evidence
- Record the reason
- Close the ticket
- Update documentation if needed

---

## Q3

What is your role during Incident Response?

Answer:
My responsibility as an L1 SOC Analyst is to monitor security alerts, perform alert triage, validate incidents, gather evidence, classify incidents, document findings, and escalate confirmed incidents to the L2 or Incident Response team.

---

## Q4

What is the purpose of Preparation?

Answer:
Preparation ensures tools, people, detection rules, and playbooks are ready before a security incident occurs.

---

## Q5

Why is Post-Incident Review important?

Answer:
It identifies lessons learned, improves detection rules, updates playbooks, and helps prevent similar incidents in the future.