# Day 27 – Interview Questions

## 1. What is Wireshark?

Wireshark is an open-source network protocol analyzer used to capture, inspect, and analyze network packets.

---

## 2. Why is Wireshark useful for SOC analysts?

Wireshark helps SOC analysts investigate network traffic, validate alerts, identify suspicious communication, analyze protocols, and collect packet-level evidence.

---

## 3. What is a packet?

A packet is a small unit of data transmitted over a network.

It contains information such as source IP, destination IP, ports, protocol, and payload.

---

## 4. What is a PCAP file?

PCAP stands for Packet Capture.

It is a file that stores captured network packets for later analysis.

---

## 5. What information can a packet contain?

A packet can contain:

- Timestamp
- Source IP
- Destination IP
- Source port
- Destination port
- Protocol
- Packet payload

---

## 6. What is the difference between capture filter and display filter?

A capture filter limits packets while traffic is being captured.

A display filter is applied after packets have already been captured to display only relevant packets.

---

## 7. Give examples of Wireshark display filters.

Examples:

tcp

udp

dns

http

ip.addr == 192.168.1.10

tcp.port == 443

---

## 8. What is the TCP three-way handshake?

The TCP three-way handshake establishes a TCP connection.

It consists of:

1. SYN
2. SYN-ACK
3. ACK

---

## 9. What are TCP flags?

TCP flags provide information about the state and behavior of a TCP connection.

Important flags include:

- SYN
- ACK
- FIN
- RST
- PSH
- URG

---

## 10. What can repeated SYN packets indicate?

A large number of SYN packets may indicate:

- Port scanning
- SYN flood attack
- Repeated connection attempts

The analyst should investigate the context before concluding that it is malicious.

---

## 11. What is DNS?

DNS stands for Domain Name System.

It translates domain names into IP addresses.

Example:

example.com → IP address

---

## 12. Why is DNS traffic important in SOC investigations?

DNS traffic can help analysts identify:

- Suspicious domains
- Malware communication
- DNS tunneling
- Unusual DNS requests
- Connections to malicious infrastructure

---

## 13. What is HTTP?

HTTP stands for Hypertext Transfer Protocol.

It is used for communication between web clients and servers.

---

## 14. What is HTTPS?

HTTPS is the secure version of HTTP.

It uses encryption to protect communication between the client and server.

---

## 15. How can Wireshark help in phishing investigations?

Wireshark can help identify:

- DNS queries
- Destination IP addresses
- Suspicious domains
- HTTP requests
- Redirects
- External connections

This can help determine what happened after a user clicked a phishing link.

---

## 16. What are suspicious network patterns an analyst should look for?

Examples include:

- Repeated connection attempts
- Unknown external IPs
- Suspicious domains
- Large data transfers
- Unusual ports
- Repeated SYN packets
- Unexpected protocols
- Suspicious HTTP requests

---

## 17. What is Protocol Hierarchy in Wireshark?

Protocol Hierarchy provides an overview of the protocols present in captured traffic.

It helps analysts understand which protocols are being used and their traffic distribution.

---

## 18. What are Endpoints in Wireshark?

Endpoints show the network addresses involved in communication.

They help identify source and destination systems.

---

## 19. What are Conversations in Wireshark?

Conversations show communication between network endpoints.

They can help analysts understand which systems communicated and how much traffic was exchanged.

---

## 20. What is an I/O Graph?

An I/O graph shows network traffic over time.

It can help identify traffic spikes and unusual network activity.

---

## 21. What is a Flow Graph?

A flow graph provides a visual representation of network communication.

It helps analysts understand communication direction and sequence.

---

## 22. How does a SOC analyst use Wireshark after receiving an alert?

A SOC analyst may:

1. Review the SIEM alert
2. Identify the affected host
3. Obtain the relevant PCAP
4. Apply Wireshark filters
5. Analyze suspicious traffic
6. Identify the source and destination
7. Validate the activity
8. Document findings
9. Escalate if necessary

---

## 23. Why are Wireshark filters important?

Filters reduce the amount of irrelevant traffic and allow analysts to focus on specific:

- IP addresses
- Ports
- Protocols
- Domains
- Connections

This makes investigations faster.

---

## 24. What is packet payload?

Payload is the actual data carried inside a packet.

Depending on the protocol and encryption, it may contain application-level information.

---

## 25. What is ARP?

ARP stands for Address Resolution Protocol.

It is used to map an IP address to a MAC address on a local network.

---

## 26. What is the difference between TCP and UDP?

TCP is connection-oriented and provides reliable communication.

UDP is connectionless and focuses on faster communication without the same reliability mechanisms as TCP.

---

## 27. What can unusual data transfer indicate?

Unusual or unexpectedly large data transfers may indicate:

- Data exfiltration
- Malware activity
- Unauthorized communication
- Compromised systems

The analyst should investigate the context before confirming malicious activity.

---

## 28. What is a suspicious DNS query?

A suspicious DNS query may involve:

- Unknown domains
- Random-looking domains
- High-frequency queries
- Domains associated with malicious activity

The analyst should correlate the query with other evidence.

---

## 29. What security precautions should be followed when handling PCAP files?

Analysts should:

- Use authorized packet captures
- Protect PCAP files
- Avoid unnecessary sharing
- Restrict access
- Preserve evidence
- Follow organizational policies

PCAP files may contain passwords, session tokens, or personal information.

---

## 30. How would you investigate suspicious traffic in Wireshark?

I would first identify the affected host and relevant time range. Then I would examine DNS, TCP, HTTP/HTTPS, and other relevant traffic using filters. I would look for suspicious IPs, domains, ports, connection patterns, and unusual data transfers. Finally, I would correlate the findings with SIEM and threat intelligence, document the evidence, and escalate the incident if required.

---

## 31. Scenario: You see many SYN packets from one IP. What would you do?

I would investigate the source IP, destination ports, number of connection attempts, and whether the TCP handshake is completing.

I would also check whether the behavior is consistent with port scanning or a SYN flood and correlate it with other security logs before escalating.

---

## 32. Scenario: A user clicked a suspicious link. How would you investigate it?

I would:

1. Identify the user's system.
2. Check DNS queries.
3. Identify the resolved IP.
4. Inspect HTTP/HTTPS connections.
5. Check redirects.
6. Identify external destinations.
7. Look for suspicious traffic or downloads.
8. Correlate with endpoint and SIEM logs.
9. Document the findings.
10. Escalate if malicious activity is confirmed.

---

## 33. Why is Wireshark important in SOC investigations?

Wireshark provides packet-level visibility into network communication.

It helps analysts validate alerts, investigate suspicious traffic, understand attack behavior, and collect network evidence.