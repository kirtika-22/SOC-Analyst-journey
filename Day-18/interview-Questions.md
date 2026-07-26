# 🎤 Day 18 – Interview Questions & Answers
## Topic: Threat Intelligence (TI) & Indicators of Compromise (IOC)

---

# 1. What is Threat Intelligence?

### Answer:
Threat Intelligence is evidence-based knowledge about cyber threats, attackers, their motives, Tactics, Techniques and Procedures (TTPs), and Indicators of Compromise (IOCs). It helps organizations detect, prevent and respond to cyber attacks effectively.

---

# 2. Why is Threat Intelligence important for a SOC Analyst?

### Answer:
Threat Intelligence helps SOC analysts:
- Add context to alerts
- Detect malicious IPs and domains
- Reduce false positives
- Improve threat hunting
- Speed up incident response
- Make better security decisions

---

# 3. What are the types of Threat Intelligence?

### Answer:

**1. Strategic Intelligence**
- High-level information
- Used by executives
- Long-term trends

**2. Tactical Intelligence**
- Focuses on attacker TTPs
- Uses MITRE ATT&CK Framework

**3. Operational Intelligence**
- Information about ongoing attack campaigns
- Malware families
- Threat actors

**4. Technical Intelligence**
- IP addresses
- Domains
- URLs
- File hashes
- Email indicators

---

# 4. What is an IOC?

### Answer:
An Indicator of Compromise (IOC) is a piece of forensic evidence that suggests a system or network has been compromised.

Examples:
- Malicious IP address
- Suspicious domain
- File hash
- Registry key
- Email header

---

# 5. Give examples of IOCs.

### Answer:
- Malicious IP Address
- Domain Name
- URL
- MD5 Hash
- SHA256 Hash
- Registry Key
- Process Name
- Email Header
- File Name

---

# 6. What is the difference between Threat Intelligence and IOC?

### Answer:

**Threat Intelligence**
- Provides context
- Explains who, why and how attackers operate

**IOC**
- Technical evidence of an attack
- Used to detect malicious activity

Threat Intelligence explains the attack, while an IOC helps detect it.

---

# 7. What is OSINT?

### Answer:
OSINT (Open Source Intelligence) is publicly available information collected from open sources to identify cyber threats.

Examples:
- VirusTotal
- AbuseIPDB
- Shodan
- AlienVault OTX

---

# 8. What is VirusTotal?

### Answer:
VirusTotal is an online threat intelligence platform that scans files, URLs and IP addresses using multiple antivirus engines and threat intelligence sources.

It helps analysts determine whether an indicator is malicious.

---

# 9. What is AbuseIPDB?

### Answer:
AbuseIPDB is a community-driven database that tracks malicious IP addresses reported for attacks such as brute force, scanning and spam.

---

# 10. What is Shodan?

### Answer:
Shodan is a search engine for internet-connected devices.

It helps analysts discover:
- Servers
- Routers
- Cameras
- Open Ports
- Services

---

# 11. What is AlienVault OTX?

### Answer:
AlienVault OTX (Open Threat Exchange) is a threat intelligence platform where security researchers share Indicators of Compromise (IOCs) and threat information.

---

# 12. What are file hashes?

### Answer:
File hashes are unique digital fingerprints of files.

Common algorithms:
- MD5
- SHA1
- SHA256

SOC analysts compare hashes to identify known malware.

---

# 13. What is a malicious domain?

### Answer:
A malicious domain is a domain used by attackers for phishing, malware delivery or command-and-control communication.

---

# 14. What is a C2 Server?

### Answer:
A Command and Control (C2) server is a server used by attackers to communicate with infected systems and issue malicious commands.

---

# 15. Where can SOC analysts find IOCs?

### Answer:
- Firewall Logs
- DNS Logs
- Proxy Logs
- Windows Event Logs
- SIEM Alerts
- EDR Logs

---

# 16. Explain the Threat Intelligence Lifecycle.

### Answer:

1. Planning
2. Collection
3. Processing
4. Analysis
5. Dissemination
6. Feedback

---

# 17. How does a SOC analyst investigate a suspicious IP?

### Answer:
1. Receive alert
2. Check VirusTotal
3. Check AbuseIPDB
4. Search firewall logs
5. Search DNS logs
6. Identify affected hosts
7. Confirm malicious activity
8. Escalate if necessary

---

# 18. What is Threat Hunting?

### Answer:
Threat Hunting is the proactive process of searching for hidden threats that may not have triggered security alerts.

---

# 19. What is the MITRE ATT&CK Framework?

### Answer:
MITRE ATT&CK is a knowledge base of attacker Tactics, Techniques and Procedures (TTPs) used by SOC analysts to understand and detect cyber attacks.

---

# 20. Which Threat Intelligence sources do you know?

### Answer:
- VirusTotal
- AbuseIPDB
- Shodan
- AlienVault OTX
- MISP
- ThreatFox
- Mandiant
- Recorded Future
- FireEye

---

# 21. Scenario Question

### Interviewer:
A firewall alert shows an outbound connection to an unknown IP. What will you do?

### Answer:
- Verify the IP using VirusTotal and AbuseIPDB.
- Check firewall and DNS logs.
- Identify affected endpoints.
- Look for additional IOCs.
- Determine whether the connection is malicious.
- Document findings.
- Escalate according to the incident response process.

---

# 22. Scenario Question

### Interviewer:
You receive a phishing email. How will you investigate it?

### Answer:
- Examine sender email.
- Analyse email headers.
- Check embedded URLs.
- Verify attachments using VirusTotal.
- Search for related IOCs.
- Block malicious indicators.
- Report and document the incident.

---

# 23. Quick Interview Revision

✅ Threat Intelligence = Knowledge about cyber threats.

✅ IOC = Evidence of compromise.

✅ OSINT = Public threat intelligence.

✅ VirusTotal = File, URL and IP reputation.

✅ AbuseIPDB = Malicious IP database.

✅ Shodan = Search engine for internet-connected devices.

✅ AlienVault OTX = IOC sharing platform.

✅ Technical Intelligence = IPs, Domains, URLs, Hashes.

✅ Threat Intelligence Lifecycle:
Planning → Collection → Processing → Analysis → Dissemination → Feedback.

---

# HR Tip

If the interviewer asks:

**"How are you learning Threat Intelligence?"**

Sample Answer:

> "I am learning Threat Intelligence by studying IOC analysis, using platforms like VirusTotal, AbuseIPDB, Shodan and AlienVault OTX. I also practise analysing IPs, domains and hashes and understand how SOC analysts use threat intelligence to investigate alerts and respond to incidents."