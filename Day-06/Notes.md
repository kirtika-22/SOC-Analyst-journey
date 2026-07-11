# Day 06 - IP Addressing Fundamentals

## Objective
Learn the fundamentals of IP addressing, subnetting, CIDR notation, and understand how IP addressing is used in Security Operations Center (SOC) investigations.

---

# What is IP Addressing?

An IP (Internet Protocol) address is a unique logical address assigned to every device connected to a network.

It allows devices to communicate over a local network or the Internet.

---

# IP Versions

## IPv4
- 32-bit address
- Written in dotted decimal format
- Example: 192.168.1.1

## IPv6
- 128-bit address
- Written in hexadecimal format
- Example:
2001:0db8:85a3:0000:0000:8a2e:0370:7334

---

# IPv4 Basics

- 32 bits long
- Divided into 4 octets
- Each octet contains 8 bits
- Each octet ranges from 0–255
- Total possible addresses: Approximately 4.3 billion

Example:
192.168.1.10

---

# IPv4 Classes

| Class | Network Bits | Host Bits | Address Range |
|--------|-------------|-----------|---------------|
| A | 8 | 24 | 1.0.0.0 – 126.255.255.255 |
| B | 16 | 16 | 128.0.0.0 – 191.255.255.255 |
| C | 24 | 8 | 192.0.0.0 – 223.255.255.255 |

---

# Public vs Private IP Addresses

## Private IP Ranges

Class A
10.0.0.0 – 10.255.255.255

Class B
172.16.0.0 – 172.31.255.255

Class C
192.168.0.0 – 192.168.255.255

### Public IP
- Routable on the Internet
- Assigned by ISP

### Private IP
- Used inside Local Area Networks (LAN)
- Cannot be accessed directly from the Internet

---

# Loopback Address

IPv4 Loopback:
127.0.0.1

Purpose:
- Tests the local machine
- Used for troubleshooting
- Verifies TCP/IP stack functionality

---

# Network and Host Portion

Every IPv4 address has:

- Network Portion → Identifies the network
- Host Portion → Identifies the device inside the network

Example:
192.168.1.20/24

Network = 192.168.1
Host = 20

---

# Subnetting

Subnetting is the process of dividing a large network into smaller logical networks.

Benefits:
- Efficient IP management
- Reduces broadcast traffic
- Improves security
- Better network performance

---

# CIDR Notation

CIDR (Classless Inter-Domain Routing) is a shortcut notation for subnet masks.

Examples:

192.168.1.0/24 → 255.255.255.0

192.168.1.0/26 → 255.255.255.192

192.168.1.0/28 → 255.255.255.240

---

# Tools to Check IP Information

Windows
- ipconfig
- ping
- tracert

Linux
- ip addr
- ifconfig
- ping
- traceroute

Online Tools
- WhatIsMyIP
- VirusTotal
- AbuseIPDB
- WHOIS

---

# Why IP Addressing is Important in SOC

SOC Analysts use IP addresses to:

- Identify attack sources
- Investigate suspicious activities
- Analyze firewall logs
- Monitor network traffic
- Differentiate internal and external devices
- Detect malicious IP addresses
- Perform threat hunting
- Correlate security events in SIEM tools

---

# Key Takeaways

- Every device needs an IP address.
- IPv4 uses 32 bits, IPv6 uses 128 bits.
- Private IPs are used inside LANs.
- Public IPs communicate over the Internet.
- CIDR simplifies subnet representation.
- Subnetting improves network efficiency.
- IP addresses are essential for SOC investigations and incident response.