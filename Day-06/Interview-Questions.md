# Day 06 - IP Addressing Interview Questions with Answers

## 1. What is an IP address?

An IP (Internet Protocol) address is a unique logical address assigned to every device on a network. It allows devices to communicate with each other over a network or the Internet.

---

## 2. Why is an IP address required?

An IP address uniquely identifies a device and enables data to be sent and received between devices.

---

## 3. What is the difference between IPv4 and IPv6?

| IPv4 | IPv6 |
|------|------|
| 32-bit | 128-bit |
| Around 4.3 billion addresses | Almost unlimited addresses |
| Decimal format | Hexadecimal format |
| Example: 192.168.1.1 | Example: 2001:db8::1 |

---

## 4. How many bits are in an IPv4 address?

IPv4 consists of **32 bits** divided into **4 octets**.

---

## 5. What is an octet?

An octet is a group of **8 bits**. An IPv4 address contains **4 octets**.

---

## 6. What is the range of each octet?

Each octet ranges from **0 to 255**.

---

## 7. What is the difference between Public and Private IP addresses?

**Public IP**
- Accessible over the Internet
- Assigned by ISP

**Private IP**
- Used within local networks
- Cannot be accessed directly from the Internet

---

## 8. What are the private IP ranges?

Class A: 10.0.0.0 – 10.255.255.255

Class B: 172.16.0.0 – 172.31.255.255

Class C: 192.168.0.0 – 192.168.255.255

---

## 9. What is the loopback address?

The IPv4 loopback address is **127.0.0.1**. It refers to the local computer.

---

## 10. Why is 127.0.0.1 used?

It is used to test the TCP/IP stack and verify that network services are working on the local machine.

---

## 11. What is a subnet mask?

A subnet mask separates the **network portion** and **host portion** of an IP address.

Example:
255.255.255.0

---

## 12. What is subnetting?

Subnetting is the process of dividing one large network into smaller logical networks to improve performance and IP management.

---

## 13. What is CIDR notation?

CIDR (Classless Inter-Domain Routing) is a shortcut notation representing the subnet mask.

Example:
192.168.1.0/24

---

## 14. What does /24 mean?

It means **24 bits are used for the network** and **8 bits for hosts**.

Subnet Mask:
255.255.255.0

---

## 15. What does /16 mean?

It means **16 bits are used for the network** and **16 bits for hosts**.

Subnet Mask:
255.255.0.0

---

## 16. What is the difference between Network ID and Host ID?

Network ID identifies the network.

Host ID identifies the specific device within that network.

---

## 17. Explain Class A, B, and C IP addresses.

Class A
- Network Bits: 8
- Host Bits: 24

Class B
- Network Bits: 16
- Host Bits: 16

Class C
- Network Bits: 24
- Host Bits: 8

---

## 18. Which command shows the IP address in Windows?

```
ipconfig
```

---

## 19. Which command shows the IP address in Linux?

```
ip addr
```

or

```
ifconfig
```

---

## 20. What is the default gateway?

A default gateway is the router that forwards traffic from the local network to other networks or the Internet.

---

# SOC-Based Questions

## 21. Why is IP addressing important in SOC?

SOC analysts use IP addresses to investigate attacks, identify malicious systems, analyze logs, monitor network traffic, and perform incident response.

---

## 22. How do you identify whether an IP is public or private?

Compare it with private IP ranges.

Example:
192.168.x.x → Private

8.8.8.8 → Public

---

## 23. How are IP addresses used in firewall logs?

Firewall logs record:
- Source IP
- Destination IP
- Port
- Protocol
- Action (Allow/Deny)

These help identify suspicious activity.

---

## 24. What information can you gather from an IP address?

- Source or destination
- Public or private
- Approximate location (public IP)
- ISP
- Reputation
- Threat intelligence

---

## 25. What would you do if multiple failed logins come from the same public IP?

- Check firewall logs
- Check SIEM alerts
- Verify user accounts
- Investigate the IP reputation
- Block the IP if confirmed malicious
- Escalate the incident

---

## 26. Why is subnetting useful in enterprise networks?

- Better IP management
- Reduces broadcast traffic
- Improves security
- Improves network performance

---

## 27. What is VirusTotal?

VirusTotal is an online threat intelligence platform used to check whether an IP, URL, domain, or file is malicious.

---

## 28. What is AbuseIPDB?

AbuseIPDB is an online database that checks whether an IP address has been reported for malicious activities.

---

## 29. How do you investigate a suspicious IP address?

1. Identify whether it is public or private.
2. Check firewall and SIEM logs.
3. Verify IP reputation using VirusTotal or AbuseIPDB.
4. Check communication history.
5. Block and escalate if necessary.

---

## 30. Which networking topic comes after IP Addressing?

- TCP vs UDP
- Port Numbers
- TCP Three-Way Handshake
- OSI Model
- DNS
- DHCP
- ARP

