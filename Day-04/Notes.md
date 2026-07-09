# Day 04 - Networking Fundamentals for SOC Analysts

## Objective

To understand the fundamentals of computer networking and their importance in Security Operations Center (SOC) operations. This knowledge helps SOC analysts analyze network traffic, investigate security alerts, and identify malicious activities.

---

# What is a Computer Network?

A computer network is a collection of interconnected devices that communicate with each other to share data, resources, and services.
or in simple words "two connected computers sharing resources with each others"

### Advantages
- Resource Sharing
- Fast Communication
- File Sharing
- Centralized Management
- Remote Access

---

# Types of Networks

## PAN (Personal Area Network)
Ultra small networks used for personal use to share data from one device to another and it can be wired or wireless.

## LAN (Local Area Network)
A network that covers a small geographical area such as a home, office, or school.

## WLAN (Wireless Local Area Network)
A LAN that's dependant on wireless connectivity or one that extends a traditional wired LAN to a wireless LAN 

## CAN (Campus Area Network)
Multiple LAN interconnected in a limited geographical are such as a corporate buiseness park, university campus.

## MAN (Metropolitan Area Network)
A network that covers an entire city or metropolitan area.

## WAN (Wide Area Network)
A network that connects devices over large geographical distances. The Internet is the largest WAN.

---

# Network Archhitectures 

Network Architecture refers to the design and structure of a computer network. It defines how devices, services, and communication protocols work together to enable data exchange between connected systems.

## 1. Client-Server Architecture
- A centralized server provides services and resources to multiple client devices.
- Commonly used in organizations and enterprises.
- Offers centralized management, better security, and easier maintenance.

## 2. Peer-to-Peer (P2P) Architecture
- All devices act as both clients and servers.
- Resources are shared directly between devices.
- Suitable for small networks but provides less security and scalability than client-server architecture.

---

# Communication Modes

Communication mode defines the direction in which data is transmitted between two devices.

## 1. Simplex Mode
- Communication occurs in only one direction.
- One device only sends data, and the other only receives.
- No feedback is possible.

**Examples:**
- Keyboard → Computer
- Television Broadcast
- Radio Transmission

---

## 2. Half-Duplex Mode
- Communication occurs in both directions, but only one device can transmit at a time.
- Devices take turns sending and receiving data.

**Examples:**
- Walkie-Talkie
- CB Radio

---

## 3. Full-Duplex Mode
- Communication occurs simultaneously in both directions.
- Both devices can send and receive data at the same time.

**Examples:**
- Telephone Calls
- Video Conferencing
- Modern Ethernet Networks

---

# Network Transmission Types

Network transmission refers to how data is delivered between devices on a network.

## 1. Unicast
- One sender communicates with one receiver.
- Most common communication type on the Internet.

**Example:**
- Sending an email to one person.

---

## 2. Broadcast
- One sender sends data to all devices on the network.

**Example:**
- ARP (Address Resolution Protocol) Request

---

## 3. Multicast
- One sender communicates with a selected group of devices.

**Example:**
- Live video streaming
- Online meetings

---

# Physical and Logical Topologies

## Physical Topology

Physical topology refers to the actual physical layout of cables, devices, and network connections.

It describes:
- How devices are physically connected.
- Cable arrangement.
- Hardware placement.

## Logical Topology

Logical topology refers to how data flows between devices regardless of the physical layout.

It describes:
- Data transmission path.
- Communication rules.
- Traffic flow.

Example:
A network may have a Star Physical Topology but use a Bus Logical Topology.

# Wired Network Topologies

## 1. Bus Topology
All devices are connected to a single backbone cable. Data travels through the backbone to reach the destination device.

## 2. Star Topology
All devices are connected to a central device such as a switch or hub. All communication passes through the central device.

## 3. Ring Topology
Each device is connected to two neighboring devices, forming a closed loop. Data travels around the ring until it reaches the destination.

## 4. Mesh Topology
Every device is connected to every other device, providing multiple communication paths.


# Wireless Network Topologies

## 1. Infrastructure Topology
Wireless devices communicate through a Wireless Access Point (AP). It is the most commonly used wireless topology in homes, offices, and enterprises.

## 2. Ad Hoc Topology
Wireless devices communicate directly with each other without using an Access Point.

## 3. Wireless Mesh Topology
Multiple wireless nodes communicate with each other to create a self-connected network, extending wireless coverage over a large area.

--- 


# Network Devices

## Router
Connects different networks and forwards data packets between them.

## Switch
Connects multiple devices within the same network and forwards data based on MAC addresses.

## Hub
Broadcasts incoming data to every connected device without filtering.

## Firewall
Monitors and filters incoming and outgoing network traffic based on predefined security rules.

## Access Point
Provides wireless connectivity to devices.

## Wireless Access Point 
WAP is a bridge that extends the wired network to the wireless network.

## Modems 
Modems modulate one signal to another such as analog to digital.

## Small Office Home Office (SOHO) Device 
All in one wireless router with expanded capabiities. 

## Dynamic Host Configuration Protocol (DHCP) Server 
Automatically assigns IP addresses to Hosts.
Makes administering a network much easier. 

## Voice Over IP (VOIP) endpoints 
Most phone sysytem runes over IP networks via dedicated protocols.  


---

# OSI Model

The OSI (Open Systems Interconnection) model consists of seven layers.


| Layer | Name | Function |
|--------|------|----------|
| 7 | Application | Provides network services to applications |
| 6 | Presentation | Data encryption and formatting |
| 5 | Session | Establishes and maintains sessions |
| 4 | Transport | Reliable data transmission (TCP/UDP) |
| 3 | Network | Routing using IP addresses |
| 2 | Data Link | Communication using MAC addresses |
| 1 | Physical | Transmission of raw bits |

---

# TCP/IP Model

The TCP/IP model consists of four layers.

- Application Layer
- Transport Layer
- Internet Layer
- Network Access Layer

It is the practical networking model used on the Internet.

---

# IP Address

An IP (Internet Protocol) address uniquely identifies a device on an IP network.

### IPv4 Example

192.168.1.10

### IPv6 Example

2001:db8::1

---

# MAC Address

A MAC (Media Access Control) address is a unique hardware address assigned to a network interface card (NIC).

First three bytes (24 bits) are assigned by the IEEE to the manufacture - organizationally unique identifier (OUI) assigned by IEEE (for example . Dell or HP)

And the last three bytes (24 bits) are usually assigned sequentially - Unique numbers 

Example:

00:1A:2B:3C:4D:5E

---

# Computer Network Protocols
Computers communicate with each other with network protocols. 
Protocols are rules governing how machines exchange data and enable effectibe communication 

## Physical Protocols
Decribe the medium,the connections and the signal

## Logical Protocols 
Software controlling how and when data is sent and received to computers, supporting pysical protocols 

---

# Firewall

A firewall is a security device that monitors and filters incoming and outgoing network traffic based on predefined rules.

Functions:

- Block unauthorized access
- Allow trusted traffic
- Monitor network communication
- Protect internal systems

---


# Why Networking is Important for SOC Analysts

A SOC Analyst uses networking knowledge to:

- Analyze network traffic
- Investigate suspicious IP addresses
- Detect malicious communication
- Identify network attacks
- Understand firewall logs
- Analyze DNS requests
- Investigate security incidents

---
