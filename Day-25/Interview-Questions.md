# Day 25 Interview Questions

## 1. What is Alert Triage?

Alert triage is the process of reviewing, validating, prioritizing, and investigating security alerts to determine whether they represent a real security incident.

---

## 2. Why is Alert Triage important?

Alert triage helps:
- Reduce alert fatigue
- Identify real threats quickly
- Filter false positives
- Improve SOC efficiency
- Prioritize critical incidents

---

## 3. What is the difference between a True Positive and a False Positive?

True Positive:
A real attack correctly detected.

False Positive:
A legitimate activity incorrectly identified as malicious.

---

## 4. What are the five steps of Alert Triage?

1. Identify Alert Context
2. Gather Evidence
3. Validate Alert
4. Determine Severity
5. Escalate or Close

---

## 5. What information do you collect during alert triage?

- Hostname
- Username
- Source IP
- Destination IP
- Timestamp
- Rule ID
- Alert Severity
- Related Logs
- Threat Intelligence Results

---

## 6. Which logs do you investigate during alert triage?

- Wazuh SIEM Logs
- Windows Event Logs
- Sysmon Logs
- EDR Logs
- Firewall Logs
- Proxy Logs

---

## 7. What tools are commonly used during Alert Triage?

- Wazuh
- Splunk
- Microsoft Sentinel
- Microsoft Defender
- CrowdStrike
- VirusTotal
- AlienVault OTX
- TheHive
- ServiceNow

---

## 8. What factors determine alert severity?

- Business impact
- Asset criticality
- Scope of attack
- Threat type
- Confidence level

---

## 9. When should an alert be escalated?

An alert should be escalated when sufficient evidence confirms it is a True Positive or requires deeper investigation by L2/L3.

---

## 10. What should you do before closing an alert?

- Verify all evidence
- Confirm it is a False Positive
- Document the investigation
- Record the reason for closure

---

## 11. What are some best practices for Alert Triage?

- Validate before escalating
- Correlate multiple logs
- Use threat intelligence
- Follow playbooks
- Document every action
- Prioritize high-severity alerts

---

## 12. Explain the SOC Alert Flow.

Security Event → Log Generated → SIEM (Wazuh) → Detection Rule → Alert Generated → L1 Analyst → Alert Triage → True Positive/False Positive → Escalate or Close

---

# Scenario-Based Questions

## Q1

Wazuh detects 30 failed login attempts from a foreign IP. What will you do?

Answer:
- Review alert details
- Identify affected host and user
- Gather related authentication logs
- Check IP reputation using VirusTotal or AlienVault OTX
- Determine whether it is a True Positive or False Positive
- Assign severity
- Document findings
- Escalate if necessary

---

## Q2

How do you decide whether an alert is High or Critical?

Answer:
I consider the business impact, asset criticality, attack scope, confidence level, and the type of threat before assigning severity.

---

## Q3

Why is documentation important during Alert Triage?

Answer:
Documentation provides investigation evidence, supports audits, improves communication between analysts, and helps during future investigations.

---

## Q4

What is your primary responsibility as an L1 SOC Analyst during Alert Triage?

Answer:
My responsibility is to monitor alerts, gather evidence, validate alerts, determine severity, document findings, and escalate confirmed incidents to L2 or the Incident Response team.