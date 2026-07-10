# Day 05 - Interview Questions (Application Layer, Ports & TCP/UDP)

## Basic Questions

### 1. What is a protocol?
**Answer:**
A protocol is a set of rules that defines how devices communicate over a network. It specifies how data is formatted, transmitted, and received.

---

### 2. What is a port?
**Answer:**
A port is a logical communication endpoint that identifies a specific application or service running on a device.

Example:
- IP Address identifies the device.
- Port identifies the application.

---

### 3. Why are ports required?
**Answer:**
Ports allow multiple applications to communicate simultaneously using the same IP address.

Example:
- Web Server
- SSH Server
- DNS Server
- Email Server

All can run on one computer because each uses a different port.

---

### 4. How many TCP/UDP ports are available?
**Answer:**
65,536 ports (0–65535).

---

### 5. What are the three port ranges?

**Answer:**

- Well-known Ports: 0–1023
- Registered Ports: 1024–49151
- Dynamic/Ephemeral Ports: 49152–65535

---

# TCP & UDP

### 6. What is TCP?

**Answer:**

TCP (Transmission Control Protocol) is a reliable, connection-oriented transport protocol that guarantees data delivery.

---

### 7. What is UDP?

**Answer:**

UDP (User Datagram Protocol) is a connectionless transport protocol that provides faster communication but does not guarantee delivery.

---

### 8. Difference between TCP and UDP?

| TCP | UDP |
|------|------|
| Connection-oriented | Connectionless |
| Reliable | Unreliable |
| Slower | Faster |
| Uses acknowledgements | No acknowledgements |
| Retransmits lost packets | No retransmission |

---

### 9. Explain the TCP Three-Way Handshake.

**Answer:**

1. Client → SYN
2. Server → SYN + ACK
3. Client → ACK

This establishes a reliable connection before data transfer.

---

### 10. Why is TCP considered reliable?

**Answer:**

Because it uses:
- Three-way handshake
- Acknowledgements
- Sequence numbers
- Checksums
- Retransmission

---

# Application Layer Protocols

### 11. What is HTTP?

**Answer:**

HTTP transfers web pages between clients and servers.

- Port: TCP 80
- Not encrypted

---

### 12. What is HTTPS?

**Answer:**

HTTPS is the secure version of HTTP that encrypts communication using SSL/TLS.

- Port: TCP 443

---

### 13. Difference between HTTP and HTTPS?

| HTTP | HTTPS |
|------|-------|
| Not encrypted | Encrypted |
| TCP 80 | TCP 443 |
| Less secure | More secure |

---

# Email Protocols

### 14. What is SMTP?

**Answer:**

SMTP (Simple Mail Transfer Protocol) is used to send emails.

Port:
- TCP 25

---

### 15. What is POP3?

**Answer:**

POP3 downloads emails from the server to the client.

Port:
- TCP 110

---

### 16. What is IMAP?

**Answer:**

IMAP keeps emails synchronized across multiple devices.

Port:
- TCP 143

---

### 17. Difference between POP3 and IMAP?

| POP3 | IMAP |
|------|------|
| Downloads emails | Syncs emails |
| Usually removes mail from server | Keeps mail on server |
| Single device | Multiple devices |

---

# File Transfer Protocols

### 18. What is FTP?

**Answer:**

FTP transfers files between computers.

Ports:
- TCP 20 (Data)
- TCP 21 (Control)

---

### 19. Why is FTP considered insecure?

**Answer:**

Because usernames, passwords, and data are transmitted in plain text.

---

### 20. What is SFTP?

**Answer:**

SFTP securely transfers files over SSH.

Port:
- TCP 22

---

### 21. What is TFTP?

**Answer:**

TFTP is a lightweight file transfer protocol.

Port:
- UDP 69

It provides no authentication or encryption.

---

# Remote Access

### 22. What is Telnet?

**Answer:**

Telnet allows remote access to devices but sends data in plain text.

Port:
- TCP 23

---

### 23. Why is SSH preferred over Telnet?

**Answer:**

SSH encrypts communication and provides secure authentication.

Port:
- TCP 22

---

### 24. What is RDP?

**Answer:**

Remote Desktop Protocol allows remote graphical access to Windows systems.

Port:
- TCP 3389

---

# Network Services

### 25. What is DNS?

**Answer:**

DNS converts domain names into IP addresses.

Port:
- UDP/TCP 53

---

### 26. What is DHCP?

**Answer:**

DHCP automatically assigns:

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server

Ports:
- UDP 67
- UDP 68

---

### 27. What is NTP?

**Answer:**

NTP synchronizes system time.

Port:
- UDP 123

---

### 28. Why is NTP important for SOC Analysts?

**Answer:**

Correct timestamps help in:

- Log correlation
- Incident investigation
- Authentication
- Event timeline analysis

---

### 29. What is SNMP?

**Answer:**

SNMP monitors and manages network devices.

Port:
- UDP 161

---

### 30. What is LDAP?

**Answer:**

LDAP is a directory service protocol used to access user and computer information.

Port:
- TCP 389

---

### 31. What is LDAPS?

**Answer:**

LDAPS is the secure version of LDAP.

Port:
- TCP 636

---

# SOC-Based Questions

### 32. Why should a SOC Analyst know port numbers?

**Answer:**

Port numbers help identify:
- Running services
- Suspicious traffic
- Malware communication
- Unauthorized access
- Data exfiltration

---

### 33. Which port is commonly targeted by brute-force attacks?

**Answer:**

- SSH → TCP 22
- RDP → TCP 3389

---

### 34. Which protocol is commonly used for phishing emails?

**Answer:**

SMTP

---

### 35. Which protocol could attackers misuse for data exfiltration?

**Answer:**

FTP

---

### 36. Which protocol is commonly abused for DNS tunneling?

**Answer:**

DNS

---

### 37. Which protocol should be used instead of Telnet?

**Answer:**

SSH

---

### 38. Which protocol keeps emails synchronized across devices?

**Answer:**

IMAP

---

### 39. Which protocol automatically assigns IP addresses?

**Answer:**

DHCP

---

### 40. Name five important ports every SOC Analyst should remember.

**Answer:**

- 22 → SSH
- 53 → DNS
- 80 → HTTP
- 443 → HTTPS
- 3389 → RDP

---

# Practical Scenario Questions

### Q1:
A SIEM alert shows repeated failed login attempts on TCP port 22. What could this indicate?

**Answer:**
Possible SSH brute-force attack.

---

### Q2:
A host sends thousands of DNS requests to unknown domains. What could this indicate?

**Answer:**
Possible DNS tunneling or malware command-and-control communication.

---

### Q3:
A user logs in successfully via RDP from an unusual country at 2 AM. What would you investigate?

**Answer:**
Check user identity, login history, source IP, geolocation, MFA logs, and whether the activity is authorized.

---

### Q4:
Why is HTTPS preferred over HTTP?

**Answer:**
HTTPS encrypts data using TLS/SSL, protecting confidentiality and integrity.

---
