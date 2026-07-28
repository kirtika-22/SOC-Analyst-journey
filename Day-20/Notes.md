# Day 20 - MITRE ATT&CK Framework

## What is MITRE ATT&CK?

MITRE ATT&CK (Adversarial Tactics, Techniques & Common Knowledge) is a knowledge base of real-world attacker behaviors created by the MITRE Corporation.

It is widely used for:

- SOC Operations
- Threat Hunting
- Detection Engineering
- Red Teaming
- Incident Response

---

# Why MITRE ATT&CK is Important

- Understand attacker behavior
- Map alerts to attacker techniques
- Improve detection rules
- Enhance incident response
- Common language for Blue Team, Red Team and Management

---

# MITRE ATT&CK vs Cyber Kill Chain

| MITRE ATT&CK | Cyber Kill Chain |
|--------------|------------------|
| Based on real-world attacks | Based on attack phases |
| Non-linear | Linear |
| Detailed techniques | High-level phases |
| Used by SOC teams | Used for attack lifecycle |

---

# ATT&CK Structure

## Tactic

The attacker's goal.

Example:
- Initial Access
- Execution
- Persistence

---

## Technique

How the attacker achieves the goal.

Example:

- Phishing
- PowerShell
- Scheduled Tasks

---

## Sub-technique

A more specific method of a technique.

Example:

PowerShell → Encoded Commands

---

## Detection

Methods used to identify attacker activity.

Examples:

- Windows Event Logs
- Sysmon Logs
- SIEM Alerts
- Command-line Monitoring

---

## Mitigation

Security controls used to prevent or reduce attacks.

Examples:

- MFA
- Patch Management
- Application Control
- Endpoint Protection

---

# ATT&CK Tactics

1. Initial Access
2. Execution
3. Persistence
4. Privilege Escalation
5. Defense Evasion
6. Credential Access
7. Discovery
8. Lateral Movement
9. Collection
10. Command and Control
11. Exfiltration
12. Impact

---

# Examples

## Initial Access

Purpose:
Gain entry into the target system.

Techniques:

- Phishing (T1566)
- Drive-by Compromise (T1189)
- Exploit Public-Facing Application (T1190)

Detection:

- Email Gateway Logs
- Web Server Logs

---

## Execution

Purpose:

Run malicious code.

Techniques:

- PowerShell (T1059.001)
- Command and Scripting Interpreter
- Exploitation for Client Execution

Detection:

- Sysmon Logs
- Command Line Logs

---

## Persistence

Purpose:

Maintain access after reboot.

Techniques:

- Registry Run Keys (T1547.001)
- Scheduled Tasks (T1053)
- Service Creation (T1543)

Detection:

- Autoruns
- Registry Monitoring
- Scheduled Task Logs

---

# MITRE ATT&CK for SOC Analysts

SOC analysts use ATT&CK to:

- Map SIEM alerts to ATT&CK techniques
- Build detection rules
- Investigate incidents
- Improve alert triage
- Understand attacker behavior

Example:

Suspicious PowerShell → Execution (T1059)

RDP Brute Force → Initial Access

---

# MITRE ATT&CK for Threat Hunting

Threat hunters use ATT&CK techniques as hunting hypotheses.

Example:

Credential Dumping

Check:

- LSASS access
- Sysmon Events
- Process Creation Logs

---

# Real-World Usage

SIEM

- Splunk
- QRadar
- Elastic

Map alerts to ATT&CK techniques.

EDR

- Microsoft Defender
- CrowdStrike Falcon
- SentinelOne

Use ATT&CK IDs during investigations.

Threat Intelligence

Threat intelligence feeds map IOCs to ATT&CK techniques (TTPs).