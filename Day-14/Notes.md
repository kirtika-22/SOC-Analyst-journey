# Day 14 - Introduction to SIEM & Wazuh

## What is SIEM?

**SIEM (Security Information and Event Management)** is a cybersecurity solution that collects, stores, analyzes, and correlates logs from multiple devices to detect security threats and generate alerts.

It acts as the **brain of a Security Operations Center (SOC)**.

---

# Why SIEM?

Organizations generate thousands of security events every day. Manual log analysis is slow and error-prone.

SIEM helps by:

- Centralizing log collection
- Detecting threats in real time
- Reducing response time
- Supporting incident investigation
- Generating compliance reports

---

# SIEM Core Functions

## 1. Data Collection
Collects logs from multiple sources such as:
- Windows
- Linux
- Firewalls
- Routers
- IDS/IPS
- Antivirus
- Cloud services
- Applications

---

## 2. Log Normalization

Converts logs from different formats into a standardized format for easier analysis.

---

## 3. Event Correlation

Analyzes multiple events together to detect suspicious patterns.

Example:
- Multiple failed login attempts
- One successful login

→ Generates a **Brute Force Alert**

---

## 4. Alerting

Automatically sends notifications when suspicious activities are detected.

Examples:
- Brute force attacks
- Malware infections
- Unauthorized access
- Privilege escalation

---

## 5. Reporting & Compliance

Generates reports required for compliance standards such as:

- PCI-DSS
- HIPAA
- ISO 27001
- GDPR

Useful during compliance audits.

---

## 6. Digital Forensics & Investigation

Helps security analysts investigate incidents using collected logs and historical events.

---

# SIEM Can Detect

- Brute Force Attacks
- Malware Outbreaks
- Insider Threats
- Data Exfiltration
- Compliance Violations
- Privilege Escalation
- Suspicious Login Activities

---

# SIEM Architecture

```
Log Sources
      │
      ▼
Collectors / Agents
      │
      ▼
   SIEM Core
      │
      ▼
Correlation Engine
      │
      ▼
Alerts & Analysis
      │
      ▼
Dashboards & Reports
```

---

# Example Log Flow

```
Endpoint Logs
      │
      ▼
Syslog / Agent
      │
      ▼
SIEM Server
      │
      ▼
Analysis
      │
      ▼
Alerts
```

---

# SIEM Tools

## Commercial

- Splunk
- IBM QRadar
- LogRhythm
- ArcSight

---

## Open Source

- Wazuh
- Elastic Stack (ELK)
- OSSIM

---

## Cloud-Based

- Microsoft Sentinel
- Google Chronicle

---

# Log Management vs SIEM

| Feature | Log Management | SIEM |
|---------|----------------|------|
| Stores Logs | ✅ | ✅ |
| Log Normalization | ❌ | ✅ |
| Real-time Analysis | ❌ | ✅ |
| Event Correlation | ❌ | ✅ |
| Alerting | ❌ | ✅ |
| Compliance Reports | ❌ | ✅ |

---

# Wazuh

Wazuh is an open-source SIEM and XDR platform used for:

- Log Collection
- Threat Detection
- File Integrity Monitoring (FIM)
- Vulnerability Detection
- Compliance Monitoring
- Endpoint Security

---

# Wazuh Components

- Wazuh Agent
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

---

# Install Wazuh Manager & Dashboard

## Update Kali Linux

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Download Installer

```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
```

---

## Install Wazuh

```bash
sudo bash wazuh-install.sh -a
```

---

# Verify Services

```bash
sudo systemctl status wazuh-manager

sudo systemctl status wazuh-dashboard

sudo systemctl status wazuh-indexer
```

---

# Dashboard URL

```
https://<Server-IP>:5601
```

Default Credentials:

Username:
```
admin
```

Password:
```
admin
```

---

# Install Wazuh Agent

Download Agent:

```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-agent-4.7.5.deb
```

Install:

```bash
sudo dpkg -i ./wazuh-agent-4.7.5.deb
```

---

# Configure Agent

Edit configuration file:

```bash
sudo nano /var/ossec/etc/ossec.conf
```

Add Manager Details:

```xml
<server>
  <address>127.0.0.1</address>
  <port>1514</port>
  <protocol>tcp</protocol>
</server>
```

---

# Register Agent

```bash
sudo /var/ossec/bin/agent-auth -m 127.0.0.1
```

---

# Start Agent

```bash
sudo systemctl enable wazuh-agent

sudo systemctl start wazuh-agent
```

---

# Verify Agent

Open:

**Wazuh Dashboard → Agents**

The connected Kali agent should appear.

---

# Monitor Agent Logs

```bash
tail -f /var/ossec/logs/ossec.log
```