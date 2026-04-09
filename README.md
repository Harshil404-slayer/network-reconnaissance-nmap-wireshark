# Network Reconnaissance: Nmap & Wireshark

## Description
This project demonstrates **network reconnaissance and packet capturing** on the `192.168.1.0/24` local network. Using **Nmap**, open ports and services on devices were identified. **Wireshark** was used to capture and analyze live network traffic to understand **TCP handshakes, DNS queries, and HTTP communication**. This project highlights **network exposure and potential security risks** associated with open ports.

---

## Tools Used
- **Kali Linux** – Operating system
- **Nmap** – Network scanning and port discovery
- **Wireshark** – Packet capturing and analysis
- **Text editor** – For documentation and notes

---

## Objectives
- Discover open ports on devices within a local network
- Understand network service exposure and security risks
- Capture and analyze network traffic at the packet level
- Learn basic network reconnaissance techniques

---

## Steps Performed

### 1. Network Scanning with Nmap
- Found local IP range using:
```bash
ip addr
Ran a TCP SYN scan with service detection on the entire subnet:
nmap -sS -sV 192.168.1.0/24 -oN Scanned_Ports.txt
Recorded open ports and services for each host
Saved scan results as Scanned_Ports.txt

# 2. Packet Capturing with Wireshark
Opened Wireshark and selected the eth0 interface for live capture
Generated traffic by:
Running the Nmap scan
Accessing the router web interface at http://192.168.1.1
Applied filters to analyze traffic:
SYN packets: tcp.flags.syn == 1
Shows Nmap scanning activity and TCP handshake initiation
Router communication: ip.addr == 192.168.1.1
Shows traffic between the local host and router
DNS packets: dns
Shows domain name resolution requests
HTTP packets: http
Shows requests to web interfaces on open ports
Saved capture as capture.pcapng and compressed as capture.zip for submission

network-reconnaissance-nmap-wireshark/
├── README.md
├── outputs/
│   ├── CapturedTraffic.pcapng.gz
│   └── Scanned_Ports.txt
├── screenshots/
    ├── scanned-ports.png
    ├── tcp-handshake.png
    ├── http-packets.png
    ├── dns-packets.png
    ├── router-communication.png
    └── captured-packets.png
# Key Learnings
Nmap SYN scan: How open ports respond to probe packets
Packet analysis: Observed TCP handshake, DNS queries, and HTTP requests
Network exposure: Identified open ports (22 SSH, 53 DNS, 80 HTTP, etc.)
Security risks: Understanding how unprotected ports could be exploited

#Usage
# 1.Clone the repository:
git clone https://github.com/your-username/network-reconnaissance-nmap-wireshark.git
# 2.Explore outputs:
Scanned_Ports.txt – port scan results
capture.zip – packet captures (open with Wireshark)
# 3.Review screenshots for visual reference of scans and packet captures
# References
Nmap Official Documentation
Wireshark Official Documentation
Ethical hacking and network security tutorials
