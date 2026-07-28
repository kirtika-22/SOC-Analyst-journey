# Day 19 - Threat Intelligence Tools Interview Questions

# Basic Questions

## Q1. What are Threat Intelligence Platforms (TIPs)?

### Answer:

Threat Intelligence Platforms are security solutions that collect, organize, analyze, and enrich threat intelligence data.

SOC analysts use TIPs to investigate indicators, enrich alerts, perform threat hunting, and improve incident response.

---

# Q2. Why do SOC analysts use Threat Intelligence Tools?

### Answer:

SOC analysts use threat intelligence tools for:

- IOC enrichment
- Investigating suspicious IPs, domains, and hashes
- Threat hunting
- Malware analysis
- Identifying threat actors
- Incident response

---

# Q3. Name some Threat Intelligence Platforms you know.

### Answer:

Some commonly used Threat Intelligence Platforms are:

- AlienVault OTX
- MISP
- Recorded Future
- ThreatConnect
- Anomali ThreatStream
- IBM X-Force Exchange
- Cisco Talos
- CrowdStrike Falcon X
- Kaspersky Threat Intelligence Portal
- Palo Alto AutoFocus
- FortiGuard Labs

---

# Tool-Based Interview Questions

---

# Q4. Explain AlienVault OTX.

### Answer:

AlienVault OTX is a community-based threat intelligence platform used for sharing and investigating threat indicators.

SOC analysts use it to check:

- IP reputation
- Domain reputation
- Malware information
- Related indicators

Example:

If a suspicious IP is detected in SIEM, an analyst can search it in OTX to verify whether it is malicious.

---

# Q5. Explain MISP.

### Answer:

MISP (Malware Information Sharing Platform) is an open-source threat intelligence sharing platform.

It helps organizations share and manage:

- IP addresses
- Domains
- Hashes
- Threat events

SOC analysts use MISP for IOC management and threat intelligence sharing.

---

# Q6. Difference between AlienVault OTX and MISP?

### Answer:

| AlienVault OTX | MISP |
|---|---|
| Community threat intelligence platform | Open-source intelligence sharing platform |
| Mainly used for searching threat information | Mainly used for managing and sharing intelligence |
| Public threat data | Organization-controlled sharing |

---

# Q7. Explain Recorded Future.

### Answer:

Recorded Future is an AI-powered threat intelligence platform that provides real-time information about cyber threats.

It helps organizations with:

- Threat actor tracking
- Vulnerability intelligence
- Dark web monitoring
- Risk analysis

SOC analysts use it for threat hunting and investigation.

---

# Q8. Explain ThreatConnect.

### Answer:

ThreatConnect is an enterprise threat intelligence platform used to manage and analyze threat intelligence.

It helps SOC teams:

- Investigate threats
- Track campaigns
- Analyze threat actors
- Manage intelligence workflows

---

# Q9. Explain Anomali ThreatStream.

### Answer:

Anomali ThreatStream is a threat intelligence management platform.

It collects threat data from multiple sources and enriches indicators.

SOC analysts use it for:

- IOC enrichment
- Alert investigation
- Threat hunting

---

# Q10. Explain IBM X-Force Exchange.

### Answer:

IBM X-Force Exchange is a threat intelligence sharing platform provided by IBM.

It provides information about:

- IP reputation
- Malware
- Vulnerabilities
- Threat reports

SOC analysts use it to investigate suspicious indicators.

---

# Q11. Explain Cisco Talos Intelligence.

### Answer:

Cisco Talos is a threat intelligence and research organization.

It provides:

- Malware intelligence
- IP reputation
- Vulnerability research
- Threat reports

SOC analysts use it for IOC investigation and malware research.

---

# Q12. Explain CrowdStrike Falcon X.

### Answer:

CrowdStrike Falcon X is a malware analysis and threat intelligence platform.

It provides:

- Malware analysis
- Threat actor intelligence
- IOC generation

SOC analysts use it for endpoint investigation and incident response.

---

# Q13. Explain Kaspersky Threat Intelligence Portal.

### Answer:

Kaspersky Threat Intelligence Portal provides malware and threat intelligence information.

It helps analysts analyze:

- Malware samples
- File hashes
- IP addresses
- Domains

---

# Q14. Explain Palo Alto AutoFocus.

### Answer:

AutoFocus is Palo Alto Networks' threat intelligence platform.

It provides:

- Malware intelligence
- Threat actor information
- Attack campaign analysis

SOC analysts use it for advanced threat investigation.

---

# Q15. Explain Check Point ThreatCloud.

### Answer:

ThreatCloud is Check Point's cloud-based threat intelligence network.

It helps detect:

- Malware
- Phishing
- Botnet activity

SOC analysts use it for threat detection and investigation.

---

# Q16. Explain Fortinet FortiGuard Labs.

### Answer:

FortiGuard Labs provides threat intelligence related to:

- Malware
- Network threats
- Vulnerabilities

SOC analysts use it to investigate suspicious network activity.

---

# Q17. Explain Flashpoint.

### Answer:

Flashpoint is a threat intelligence platform focused on cybercrime and underground intelligence.

It helps monitor:

- Dark web activity
- Data leaks
- Criminal activities

SOC teams use it for risk monitoring.

---

# Q18. Explain Digital Shadows SearchLight.

### Answer:

Digital Shadows SearchLight provides external threat monitoring and digital risk protection.

It detects:

- Credential leaks
- Data exposure
- Brand impersonation

---

# Q19. Explain IntSights.

### Answer:

IntSights is an external threat intelligence platform focused on attack surface monitoring.

It helps detect:

- Fake websites
- Phishing campaigns
- External threats

---

# Q20. Explain ReversingLabs.

### Answer:

ReversingLabs focuses on malware analysis and software supply chain security.

It helps analyze:

- Suspicious files
- Malware
- Software risks

---

# Q21. Explain EclecticIQ.

### Answer:

EclecticIQ is an enterprise threat intelligence platform used for managing intelligence operations.

It helps with:

- Threat investigation
- Threat hunting
- Intelligence analysis

---

# Q22. Explain ThreatQ.

### Answer:

ThreatQ is a threat intelligence management platform.

It helps SOC teams:

- Collect intelligence
- Enrich alerts
- Automate workflows

---

# Scenario-Based Questions

---

# Q23. A SIEM alert shows a suspicious IP address. How will you investigate?

### Answer:

Steps:

1. Collect the IP address from the alert.
2. Search the IP in threat intelligence platforms.
3. Check reputation and previous reports.
4. Identify related domains or malware.
5. Check internal logs.
6. Decide action:
   - Block
   - Monitor
   - Escalate

---

# Q24. A user downloads a suspicious file. How will you investigate?

### Answer:

Steps:

1. Collect file hash.
2. Check hash reputation using threat intelligence tools.
3. Analyze malware information.
4. Check endpoint activity.
5. Search for related indicators.
6. Take containment action.

---

# Q25. How do you enrich an IOC?

### Answer:

IOC enrichment can be done by checking:

- IP reputation
- Domain reputation
- Malware details
- Threat actor information
- Related campaigns

Using tools like:

- AlienVault OTX
- MISP
- Recorded Future
- ThreatConnect
- IBM X-Force Exchange

---

# Q26. Which Threat Intelligence tools have you studied?

### Answer:

"I have studied multiple Threat Intelligence Platforms including AlienVault OTX, MISP, Recorded Future, ThreatConnect, Anomali ThreatStream, IBM X-Force Exchange, Cisco Talos, CrowdStrike Falcon X, Kaspersky Threat Intelligence Portal, Palo Alto AutoFocus, FortiGuard Labs, and other enterprise intelligence platforms."

---

# Q27. Which Threat Intelligence tool is most useful for a SOC Analyst?

### Answer:

The most useful tools depend on the organization, but commonly used platforms include:

- AlienVault OTX for IOC investigation
- MISP for intelligence sharing
- Recorded Future for advanced threat intelligence
- ThreatConnect and Anomali for enterprise intelligence management
