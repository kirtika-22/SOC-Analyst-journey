# Day 27 – Wireshark for SOC Investigations

## 1. Introduction to Wireshark

Wireshark is a network protocol analyzer used to capture, inspect, and analyze network packets.

It is commonly used by SOC analysts for:
- Network monitoring
- Security investigations
- Packet analysis
- Alert validation
- Troubleshooting suspicious network activity

---

## 2. Why Packets Are Important in SOC

Packets contain information about network communication.

By analyzing packets, a SOC analyst can understand:
- Who communicated with whom
- Which protocol was used
- What ports were involved
- What data was exchanged
- Whether the traffic is suspicious

Packet analysis helps analysts investigate security incidents in detail.

---

## 3. What is Wireshark?

Wireshark is an open-source network protocol analyzer.

It allows analysts to:
- Capture live network traffic
- Open and analyze PCAP files
- Inspect packet headers
- Analyze protocols
- Follow network conversations
- Identify suspicious traffic patterns

---

## 4. Key Capabilities of Wireshark

Important capabilities include:

1. View raw network traffic
2. Capture network packets
3. Inspect packet headers
4. Analyze suspicious traffic
5. Apply filters
6. Follow network conversations
7. Analyze protocols
8. View statistics and graphs

---

## 5. How SOC Analysts Use Wireshark

A SOC analyst may use Wireshark when investigating:
- Suspicious network connections
- Malware communication
- Phishing incidents
- DNS anomalies
- Unusual HTTP/HTTPS traffic
- Port scanning
- Network attacks
- Data transfer anomalies

---

## 6. Packet Capture Basics

### What is a Packet?

A packet is a small unit of data transmitted over a network.

A packet contains information such as:
- Source IP
- Destination IP
- Source port
- Destination port
- Protocol
- Packet data/payload

---

## 7. What is a PCAP File?

PCAP stands for Packet Capture.

A PCAP file stores captured network packets for later analysis.

A PCAP may contain:
- Timestamp
- Source IP
- Destination IP
- Port number
- Protocol information
- Packet payload

Typical PCAP files can range from a few MB to several GB.

SOC investigations may start with a single PCAP file such as:

incident-name.pcap

---

## 8. Packet Structure

A packet contains different layers of information.

Important parts include:

1. Ethernet Header
2. IP Header
3. TCP/UDP Header
4. Application Data

### Ethernet Header

Contains information such as:
- Source MAC address
- Destination MAC address

### IP Header

Contains:
- Source IP
- Destination IP
- Protocol
- Other IP-related information

### TCP/UDP Header

Contains:
- Source port
- Destination port
- TCP/UDP information

### Payload

Contains the actual data carried by the packet.

---

## 9. Important Protocols for Packet Analysis

### ARP

ARP stands for Address Resolution Protocol.

It maps an IP address to a MAC address.

Example:

IP: 192.168.1.10
MAC: AA:BB:CC:DD:EE:FF

---

### DNS

DNS converts domain names into IP addresses.

Example:

google.com → IP address

SOC analysts can use DNS traffic to identify:
- Suspicious domains
- Malicious domains
- DNS tunneling
- Unusual DNS requests

---

### HTTP/HTTPS

HTTP is used for web communication.

HTTPS is the encrypted version of HTTP.

SOC analysts can investigate:
- HTTP requests
- HTTP responses
- Suspicious URLs
- Redirects
- Web-based attacks

---

### TCP

TCP is a connection-oriented protocol.

It provides reliable communication between systems.

---

### UDP

UDP is a connectionless protocol.

It is commonly used for:
- DNS
- Streaming
- VoIP
- Other fast network communication

---

## 10. TCP Three-Way Handshake

TCP establishes a connection using a three-way handshake.

The three steps are:

1. SYN
2. SYN-ACK
3. ACK

Example:

Client → SYN → Server
Server → SYN-ACK → Client
Client → ACK → Server

After this, communication can begin.

---

## 11. TCP Flags

Important TCP flags include:

- SYN – Starts a TCP connection
- ACK – Acknowledges received data
- FIN – Gracefully closes a connection
- RST – Resets a connection
- PSH – Pushes data to the application
- URG – Indicates urgent data

### Security Relevance

A large number of SYN packets without successful connections may indicate:
- Port scanning
- SYN flood attack
- Suspicious connection attempts

---

## 12. Wireshark Filters

Filters help analysts focus on relevant traffic.

### Display Filters

Display filters are applied after packets are captured.

Examples:

tcp

udp

dns

http

ip.addr == 192.168.1.10

tcp.port == 443

dns.qry.name == "example.com"

---

### Capture Filters

Capture filters are used while capturing traffic.

They limit which packets are captured.

Example:

host 192.168.1.10

port 80

tcp

---

## 13. Why Filters Are Important

Large PCAP files may contain thousands or millions of packets.

Filters help analysts:
- Reduce noise
- Focus on relevant traffic
- Investigate specific IPs
- Investigate specific ports
- Identify suspicious protocols
- Save investigation time

---

## 14. Following Network Conversations

Wireshark allows analysts to follow network conversations.

This helps understand:
- Who communicated with whom
- What protocol was used
- What traffic was exchanged
- How a connection developed

For example:

Client → Web Server → Response

This can help reconstruct an attack or suspicious communication.

---

## 15. Identifying Suspicious Traffic

SOC analysts should look for unusual patterns such as:

- Unknown external IP addresses
- Repeated connection attempts
- Large data transfers
- Suspicious DNS requests
- Unusual ports
- Repeated SYN packets
- Unexpected protocols
- Suspicious HTTP requests
- Connections to malicious domains

---

## 16. Wireshark Statistics and Visual Tools

Wireshark provides several tools to understand traffic quickly.

Important tools include:

1. Protocol Hierarchy
2. Endpoints
3. Conversations
4. I/O Graphs
5. Flow Graph

---

## 17. Protocol Hierarchy

Protocol Hierarchy shows the protocols present in captured traffic.

It helps analysts understand:
- Which protocols are being used
- How much traffic each protocol generates
- Whether an unusual protocol is present

---

## 18. Endpoints

Endpoints show communicating network addresses.

They can help identify:
- Source systems
- Destination systems
- Internal hosts
- External hosts

---

## 19. Conversations

Conversations show communication between endpoints.

They help analysts determine:
- Which systems communicated
- How much data was exchanged
- Which ports were used

---

## 20. I/O Graphs

I/O graphs show network traffic over time.

They can help identify:
- Traffic spikes
- Unusual activity
- Large bursts of network communication

---

## 21. Flow Graph

A flow graph provides a visual representation of communication.

It helps analysts quickly understand:
- Communication direction
- Source and destination
- Protocols
- Sequence of communication

---

## 22. Wireshark in SOC Workflow

A typical SOC workflow can be:

1. SIEM alert is triggered
2. Analyst pulls the related PCAP
3. Analyst applies relevant filters
4. Analyst investigates the traffic
5. Analyst checks for anomalies
6. Analyst updates the incident ticket
7. Analyst escalates to L2/IR team if required

Wireshark enhances network investigations by providing packet-level evidence.

---

## 23. Wireshark for Suspicious Network Investigations

SOC analysts can investigate:

### Suspicious DNS Requests

Look for:
- Unknown domains
- Random-looking domain names
- High-frequency DNS queries
- Suspicious external domains

### Repeated SYN Packets

May indicate:
- Port scanning
- SYN flood
- Repeated connection attempts

### HTTP Redirects

Multiple or suspicious redirects may indicate:
- Phishing
- Malicious websites
- Malware communication

### Unusual Data Transfer

Large or unexpected transfers may indicate:
- Data exfiltration
- Malware activity
- Unauthorized communication

---

## 24. Phishing Investigation Using Wireshark

Wireshark can help investigate network activity related to phishing.

An analyst can examine:
- Destination IP
- Domain name
- DNS requests
- HTTP requests
- Redirects
- External connections

Example:

User receives phishing email
        ↓
User clicks malicious link
        ↓
DNS request is generated
        ↓
Connection to malicious server
        ↓
HTTP/HTTPS traffic
        ↓
Analyst investigates PCAP

---

## 25. Suspicious External Connections

An analyst should investigate connections to:
- Unknown external IPs
- Suspicious domains
- Newly observed destinations
- Unexpected geographic locations
- Known malicious infrastructure

The analyst should correlate these findings with SIEM, threat intelligence, and endpoint logs.

---

## 26. What You Should NOT Do With Wireshark

1. Do not capture packets on production servers without authorization.
2. Do not run Wireshark with unnecessary administrative privileges.
3. Do not capture traffic without approval.
4. Do not share PCAP files containing sensitive information.

PCAP files may contain:
- Passwords
- Session tokens
- Personal information
- Sensitive application data

Therefore, PCAP files must be handled securely.

---

## 27. PCAP as Investigation Evidence

PCAP files can be valuable evidence during security investigations.

Analysts should:
- Preserve the original file
- Avoid modifying evidence
- Record investigation findings
- Maintain proper access control
- Document important packets and timestamps

---

## 28. SOC Case Investigation Using Wireshark

A basic investigation process:

1. Investigate suspicious alert
2. Analyze the network traffic
3. Inspect DNS queries
4. Check HTTP/HTTPS traffic
5. Identify suspicious IPs/domains
6. Analyze TCP connections
7. Look for unusual traffic patterns
8. Validate findings using other security tools
9. Document evidence
10. Escalate if required