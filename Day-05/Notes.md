# Day 05 - Application Layer Protocols, Ports & TCP/UDP Fundamentals

## Objective

Today I learned how Application Layer protocols work, why port numbers are important, and how TCP and UDP differ. I also explored common protocols that SOC Analysts frequently encounter during log analysis, threat detection, and incident investigations.

---

# Why Ports and Protocols Matter for SOC Analysts

SOC Analysts constantly analyze:

- Network traffic
- Firewall logs
- IDS/IPS alerts
- SIEM logs
- Packet captures (Wireshark)
- Authentication events

Understanding protocols and ports helps identify:

- Legitimate traffic
- Suspicious connections
- Malware communication
- Data exfiltration
- Unauthorized remote access

---

# What is a Protocol?

A protocol is a set of rules that defines how devices communicate over a network.

Examples:

- HTTP
- HTTPS
- FTP
- SSH
- SMTP
- DNS

Protocols define:

- Data format
- Communication method
- Error handling
- Security

---

# What is a Port?

A port is a logical communication endpoint that allows multiple applications to use the same IP address.

Example:

A computer may have one IP address but can run:

- Web Server
- Email Server
- SSH Service
- DNS Service

Ports identify which application should receive the traffic.

Example:

```
192.168.1.80:80
```

- IP Address → identifies the device
- Port → identifies the application

---

# Port Categories

| Port Range | Type |
|------------|------|
| 0 – 1023 | Well-Known Ports |
| 1024 – 49151 | Registered Ports |
| 49152 – 65535 | Dynamic / Ephemeral Ports |

---

# Common Ports Every SOC Analyst Should Know

| Protocol | Port | Transport |
|----------|------|-----------|
| FTP | 20,21 | TCP |
| SFTP | 22 | TCP |
| SSH | 22 | TCP |
| Telnet | 23 | TCP |
| SMTP | 25 | TCP |
| DNS | 53 | UDP/TCP |
| DHCP | 67,68 | UDP |
| TFTP | 69 | UDP |
| HTTP | 80 | TCP |
| POP3 | 110 | TCP |
| NTP | 123 | UDP |
| IMAP | 143 | TCP |
| SNMP | 161 | UDP |
| LDAP | 389 | TCP |
| HTTPS | 443 | TCP |
| SMB | 445 | TCP |
| LDAPS | 636 | TCP |
| RDP | 3389 | TCP |
| SIP | 5060/5061 | UDP/TCP |

---

# TCP vs UDP

## TCP

Transmission Control Protocol

Characteristics:

- Connection-oriented
- Reliable
- Ordered delivery
- Error checking
- Retransmits lost packets
- Uses acknowledgements

Reliable because of:

- Three-way handshake
- Sequence numbers
- Checksums
- Acknowledgements
- Retransmission

Common Uses:

- Web browsing
- SSH
- HTTPS
- Email
- FTP

---

## UDP

User Datagram Protocol

Characteristics:

- Connectionless
- Faster
- No acknowledgements
- No retransmission
- Lower overhead

Best suited for:

- Live video
- Voice calls (VoIP)
- Online gaming
- Streaming
- DNS
- DHCP
- NTP

---

# TCP Three-Way Handshake

Connection establishment process:

```
Client → SYN

Server → SYN + ACK

Client → ACK
```

Purpose:

- Establishes a reliable connection before data transmission.

---

# Application Layer Protocols

## HTTP (HyperText Transfer Protocol)

Purpose:

Transfers web pages between browser and server.

Default Port:

- TCP 80

Security:

- Not encrypted

SOC Importance:

- Detect malicious web traffic
- Analyze HTTP requests
- Detect Command & Control communication

---

## HTTPS (HyperText Transfer Protocol Secure)

Purpose:

Secure version of HTTP using TLS/SSL encryption.

Default Port:

- TCP 443

Benefits:

- Encryption
- Integrity
- Authentication

SOC Importance:

- Detect suspicious encrypted traffic
- SSL certificate analysis
- HTTPS inspection

---

# Email Protocols

## SMTP (Simple Mail Transfer Protocol)

Purpose:

Sends emails between mail servers.

Default Port:

- TCP 25

SOC Use Cases:

- Email spoofing
- Phishing
- Spam detection
- Malware delivery

---

## POP3 (Post Office Protocol v3)

Purpose:

Downloads emails from the server to the client.

Default Port:

- TCP 110

Characteristics:

- Emails are usually removed from the server after download.
- Best for accessing mail on one device.

---

## IMAP (Internet Message Access Protocol)

Purpose:

Synchronizes emails across multiple devices.

Default Port:

- TCP 143

Characteristics:

- Emails remain on the server.
- Supports multiple devices.

---

# File Transfer Protocols

## FTP

Purpose:

Transfers files between systems.

Ports:

- TCP 20 (Data)
- TCP 21 (Control)

Limitations:

- Sends data in plain text
- Insecure

SOC Concern:

- Credential theft
- Data exfiltration

---

## SFTP

Purpose:

Secure file transfer over SSH.

Port:

- TCP 22

Advantages:

- Encrypted communication
- Secure authentication

---

## TFTP

Purpose:

Simple file transfer.

Port:

- UDP 69

Limitations:

- No authentication
- No encryption

Commonly used for:

- Network device booting
- Firmware transfer

---

# Remote Access Protocols

## Telnet

Purpose:

Remote device management.

Port:

- TCP 23

Issue:

- Sends credentials in plain text.

Today mostly replaced by SSH.

---

## SSH

Purpose:

Secure remote administration.

Port:

- TCP 22

Features:

- Encrypted communication
- Secure authentication
- File transfer support

SOC Importance:

- Monitor remote logins
- Detect brute-force attacks
- Investigate unauthorized access

---

## RDP (Remote Desktop Protocol)

Purpose:

Remote desktop access.

Port:

- TCP 3389

SOC Importance:

- Frequently targeted by attackers
- Monitor failed logins
- Detect brute-force attacks
- Identify unauthorized remote sessions

---

# Network Services

## DNS

Purpose:

Converts domain names into IP addresses.

Port:

- UDP/TCP 53

SOC Importance:

- DNS tunneling detection
- Malware beaconing
- Suspicious domain investigation

---

## DHCP

Purpose:

Automatically assigns:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

Ports:

- UDP 67
- UDP 68

---

## NTP

Purpose:

Synchronizes system time.

Port:

- UDP 123

SOC Importance:

Accurate timestamps are critical for:

- Log correlation
- Incident response
- Authentication

---

## SNMP

Purpose:

Network monitoring and management.

Port:

- UDP 161

Can monitor:

- CPU usage
- Memory
- Interface status
- Bandwidth

SOC Importance:

Useful for detecting unusual device behavior.

---

## LDAP

Purpose:

Directory service protocol for user authentication and directory queries.

Port:

- TCP 389

Stores:

- Users
- Groups
- Computers
- Organizational Units

---

## LDAPS

Purpose:

Secure LDAP using SSL/TLS.

Port:

- TCP 636

Provides encrypted directory communication.

---

# Real-World SOC Scenarios

### Scenario 1

Multiple failed login attempts on TCP Port 22.

Possible Attack:

- SSH Brute Force Attack

---

### Scenario 2

Large outbound FTP traffic during midnight.

Possible Attack:

- Data Exfiltration

---

### Scenario 3

Hundreds of DNS requests to unknown domains.

Possible Attack:

- Malware Command & Control
- DNS Tunneling

---

### Scenario 4

Thousands of connection attempts to TCP Port 3389.

Possible Attack:

- RDP Brute Force

---

### Scenario 5

User accesses a phishing website over HTTP.

Possible Detection:

- Web Proxy Logs
- Firewall Logs
- IDS Alerts

---

# Key Takeaways

- Learned the importance of ports and protocols.
- Understood TCP vs UDP and their use cases.
- Studied common Application Layer protocols.
- Learned email, file transfer, remote access, and network management protocols.
- Explored how SOC Analysts use protocol knowledge during monitoring and incident response.
- Practiced real-world attack scenarios involving common network services.

---

## Skills Practiced

- Networking Fundamentals
- Application Layer Protocols
- TCP/IP
- Port Identification
- Email Protocols
- Remote Access Protocols
- Network Services
- SOC Fundamentals
- Security Monitoring
- Incident Analysis

---

## Progress

**Networking for SOC Analyst — Day 05 Completed ✅**