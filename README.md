# Investigating Local Network Security Through Port Scanning and Packet Capture

**Description:**
This project evaluates local network security using Nmap and Wireshark by identifying open ports, services, and vulnerabilities. It performs device discovery, TCP SYN scans, and analyzes ARP/SYN packets to detect risks, map services, study traffic, and strengthen network defenses.

All IP addresses are sanitized (last octet masked) and all MAC addresses removed for privacy.

---

## 📌 1. Find Your Local IP Range

Using the command:

```
ipconfig
```

I identified:
- **IPv4:** 192.168.1.xx  
- **Subnet Mask:** 255.255.255.0  

This subnet mask indicates a **/24 network**, meaning the scan range is:

```
192.168.1.0/24
```

---
