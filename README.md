# Investigating Local Network Security Through Port Scanning and Packet Capture

**Description:**
This project evaluates local network security using Nmap and Wireshark by identifying open ports, services, and vulnerabilities. It performs device discovery, TCP SYN scans, and analyzes ARP/SYN packets to detect risks, map services, study traffic, and strengthen network defenses.

All IP addresses are sanitized (last octet masked) and all MAC addresses removed for privacy.

---

## 📌 1. Find Your Local IP Range

Using the command:

```
ifconfig
```

I identified:
- **IPv4:** 192.168.1.xx  
- **Subnet Mask:** 255.255.255.0  

This subnet mask indicates a **/24 network**, meaning the scan range is:

```
192.168.1.0/24
```

---

## 📌 2. Discover Live Hosts (Ping/ARP Scan)

Before scanning ports, I first identified which devices are active on the network using:

```
nmap -sn 192.168.1.0/24
```

### ✔ What the `-sn` Scan Does:
- Performs host discovery only
- Sends **ARP requests** on local networks
- Identifies all devices that respond
- Does not perform any port scanning

In Wireshark, this corresponds to ARP traffic such as:
- “Who has 192.168.1.X?”
- Devices replying with their MAC addresses (redacted)

This phase verifies which IPs are active on the network before proceeding with the TCP SYN port scan.

---
