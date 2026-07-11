# Week 02 Assignment — Computer Networking Fundamentals & Network Configuration

**IT-SIMPLERA Institute — Cyber Security Analyst Internship Program**

| | |
|---|---|
| **Student Name** | Rayan Ayub |
| **Registration No.** | REDB01-1766 |
| **Role** | Red Team Intern |
| **Institute** | IT-SIMPLERA Institute |
| **Supervisor** | Talal Rehan |
| **Week** | Week 02 |
| **Submission Date** | 11 July 2026 |

📄 Full report: [`Week2_Networking_Assignment_Final.docx`](./Week2_Networking_Assignment_Final.docx)

---

## Table of Contents

- [Introduction](#introduction)
- [Q1. Understanding Your Network Information](#q1-understanding-your-network-information)
- [Q2. Basic Networking Commands](#q2-basic-networking-commands)
- [Q3. Router vs Switch](#q3-router-vs-switch)
- [Q4. IPv4 vs IPv6](#q4-ipv4-vs-ipv6)
- [Q5. The OSI Model](#q5-the-osi-model)
- [Network Diagram](#network-diagram)
- [Conclusion](#conclusion)

---

## Introduction

Networking is how computers talk to each other. Every time we open a website, send an email, or stream a video, our device is using a network to send and receive data. Understanding how networks work is one of the first and most important steps in cyber security, because most attacks happen over a network, and most defenses depend on understanding how that network is supposed to behave.

This assignment covers reading a computer's network settings, using basic networking commands, comparing routers with switches, comparing IPv4 with IPv6 addressing, and going through the seven layers of the OSI Model.

---

## Q1. Understanding Your Network Information

Command used: `ipconfig /all`

**IPv4 Address**
- IPv4 consists of 32 bits, divided into four 8-bit octets.
- It works like a home address for a device on a network.
- Every device on the network has its own unique IPv4 address.
- Example: `192.168.1.100`

**MAC Address**
- A unique physical address assigned to a network interface card by its manufacturer.
- 48 bits (6 bytes) long, usually written as six pairs of hex digits separated by `:` or `-`.
- Example: `00:1A:2B:3C:4D:5E`

**Default Gateway**
- The network device that forwards data from the local network to other networks.
- When a device wants to reach something outside its own network, it sends the data to the default gateway, which routes it onward.
- Example: `192.168.1.1`

**Screenshots:**

| ipconfig /all (part 1) | ipconfig /all (part 2) |
|---|---|
| ![ipconfig part 1](./screenshots/01-ipconfig-all-part1.png) | ![ipconfig part 2](./screenshots/02-ipconfig-all-part2.png) |

---

## Q2. Basic Networking Commands

### 1. `ipconfig /all`
Shows all network details of a computer in one place: IPv4 address, IPv6 address, MAC address, DNS servers, DHCP status, and default gateway.
**Why it matters:** Usually the first command a security analyst runs to check how a machine is set up on the network.

### 2. `ping google.com`
Sends a few packets (ICMP Echo Requests) to a host and waits for a reply, to check connectivity.
**Why it matters:** A quick way to check if the internet is working, if a server is online, and how much delay or data loss exists.

![ping google.com](./screenshots/03-ping-google.png)

### 3. `tracert google.com`
Shows every router (hop) a message passes through on its way to a destination, along with how long each hop takes.
**Why it matters:** Helps locate exactly where a connection is slowing down or failing.

![tracert google.com](./screenshots/04-tracert-google.png)

### 4. `nslookup google.com`
Asks a DNS server to translate a domain name into its IP address.
**Why it matters:** Used to verify DNS records or investigate suspicious domains, such as those used in phishing.

![nslookup google.com](./screenshots/05-nslookup-google.png)

### 5. `arp -a`
Shows the ARP table — the list of IP addresses and their matching MAC addresses on the local network.
**Why it matters:** Useful for spotting ARP spoofing and identifying active devices on the network.

![arp -a](./screenshots/06-arp-a.png)

---

## Q3. Router vs Switch

| Feature | Router | Switch |
|---|---|---|
| Main Job | Connects two or more different networks | Connects devices on the same network |
| OSI Layer | Layer 3 (Network Layer) | Layer 2 (Data Link Layer) |
| Address Used | IP address | MAC address |
| How Traffic Moves | Sends packets between different networks | Sends frames between devices on the same LAN |
| Internet Access | Gives a network access to the internet | Does not connect to the internet on its own |
| Typical Use | Home router, office router | Office LAN switch |

In short: routers move data between different networks using IP addresses, while switches move data between devices inside one network using MAC addresses. A typical office needs both.

---

## Q4. IPv4 vs IPv6

| Feature | IPv4 | IPv6 |
|---|---|---|
| Address Length | 32-bit | 128-bit |
| How It's Written | Numbers, e.g. `192.168.1.10` | Hexadecimal, e.g. `2001:0db8:85a3:0000:0000:8a2e:0370:7334` |
| Total Addresses Available | About 4.3 billion | 340 undecillion |
| Security | Encryption is optional | Encryption is built in |
| Broadcast | Supported | Not supported — uses multicast instead |
| Header Size | More complex | Simpler and faster to process |

- Example IPv4 address: `192.168.1.10`
- Example IPv6 address: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`

IPv6 was created because the world was running out of IPv4 addresses, and provides a far larger address space with better built-in security.

---

## Q5. The OSI Model

The OSI Model breaks down everything that happens when two devices communicate into seven layers, from the physical cable up to the application in use.

![OSI Model diagram](./screenshots/07-osi-model-diagram.png)

![OSI Model layer breakdown](./screenshots/08-osi-model-table.png)

---

## Network Diagram

A simple example of how these pieces fit together: end devices connect to a switch, the switch connects to a router, and the router connects the whole network to the internet.

![Network topology diagram](./screenshots/09-network-topology-diagram.png)

---

## Conclusion

This assignment covered the basic building blocks of networking: reading a device's network settings, using simple commands to check and troubleshoot a connection, understanding the difference between routers and switches, comparing IPv4 with IPv6, and going through the seven layers of the OSI Model. These fundamentals form the foundation that most cyber security work builds on.

---

*Submitted as part of the IT-SIMPLERA Institute Cyber Security Analyst Internship Program — Week 02.*
