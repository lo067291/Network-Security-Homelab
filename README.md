# Enterprise Network Security Homelab

![Status](https://img.shields.io/badge/Status-Active-green)
![pfSense](https://img.shields.io/badge/Firewall-pfSense-blue)
![Kali](https://img.shields.io/badge/Attack-Kali_Linux-red)
![Snort](https://img.shields.io/badge/IDS/IPS-Snort-orange)
![Ubuntu](https://img.shields.io/badge/Target-Ubuntu_Server-purple)

## 🎯 Project Overview
Enterprise-grade network security lab simulating classified defense 
infrastructure with multiple security zones, firewall segmentation, 
Snort IDS/IPS, and real penetration testing capabilities.

Built to demonstrate practical application of CompTIA Network+ and 
Security+ knowledge in a real-world environment.

---

## 🏗️ Network Architecture

                INTERNET
                   |
          [WAN: em0 - NAT]
                   |
          ┌────────────────┐
          │  pfSense       │
          │  Firewall +    │
          │  Snort IDS/IPS │
          └────────────────┘
                   |
      ┌────────────┴────────────┐
      │                         │
  [LAN: em1]                 [OPT1: em2]
192.168.1.0/24             192.168.2.0/24
Internal Network                DMZ
      │                         │
[Kali Linux]              [Ubuntu Server]
Attack Machine            Target (SSH+HTTP)
---

## 🔧 Technologies Used

| Technology | Purpose | Version |
|------------|---------|---------|
| pfSense | Firewall/Router | v1.2 RELEASE |
| Snort | IDS/IPS | Latest |
| Kali Linux | Penetration Testing | 2024.x |
| Ubuntu Server | Attack Target | 22.04 LTS |
| VirtualBox | Virtualization | 7.0 |
| Apache2 | Web Server (Target) | 2.4.x |

---

## 🔒 Security Zones

### WAN (Internet Facing)
- NAT interface connecting to internet
- All inbound traffic blocked by default
- Only established connections allowed back in

### Internal Network - 192.168.1.0/24
- Houses Kali Linux attack machine
- Security team/analyst network
- Full access for penetration testing

### DMZ - 192.168.2.0/24
- Houses Ubuntu Server target
- Running SSH (port 22) and HTTP (port 80)
- Monitored by Snort IDS/IPS
- Simulates public-facing services zone

---

## 📊 Lab Capabilities

### ✅ Completed (Week 1) - Foundation
- pfSense firewall installation and configuration
- Network segmentation (3 security zones)
- DHCP configuration for all zones
- Web-based firewall management (WebGUI)
- Kali Linux attack machine deployment
- Network connectivity verified between zones

### ✅ Completed (Week 2) - Attack & Defense
- Snort IDS/IPS installed and configured on pfSense
- Ubuntu Server deployed in DMZ as target
- Apache2 web server installed on target
- SSH service configured on target
- Nmap port scans executed from Kali
- Vulnerability scans executed from Kali
- Snort successfully detected attack traffic
- Penetration test results documented

### 🔄 In Progress (Week 3)
- SSH brute force attacks with Hydra
- Web application attacks against Apache
- Metasploit exploitation attempts
- Full incident response documentation

### 📋 Planned (Week 4)
- Centralized logging (ELK Stack)
- Full security audit report
- Defense recommendations
- Network hardening implementation

---

## 🖥️ Lab Environment

| VM | OS | IP Address | Role | Network |
|----|-----|------------|------|---------|
| pfSense-Firewall | pfSense CE | 192.168.1.1 / 192.168.2.1 | Firewall/IPS | All zones |
| Kali-Attack | Kali Linux | 192.168.1.10 | Attack Machine | Internal |
| Ubuntu-Server | Ubuntu 22.04 | 192.168.2.10 | Target Server | DMZ |

---

## 🔴 Week 2 - Penetration Testing Results

### Attack Summary
- **Attacker:** Kali Linux (192.168.1.10)
- **Target:** Ubuntu Server (192.168.2.10)
- **IPS:** Snort on pfSense

### Open Ports Discovered
| Port | Service | Version |
|------|---------|---------|
| 22 | SSH | OpenSSH |
| 80 | HTTP | Apache 2.4 |

### Commands Used
```bash
# Service detection scan
nmap -sV -sC -A -T4 -Pn 192.168.2.10

# Vulnerability scan
nmap --script=vuln -Pn 192.168.2.10
```

### Snort IPS Response
- ✅ Detected port scanning activity
- ✅ Generated caution alerts for suspicious traffic
- ✅ Logged all attack attempts

---

## 📸 Screenshots

### Week 1 - Foundation
| Screenshot | Description |
|------------|-------------|
| [pfSense Dashboard pt1](screenshots/pfSense%20Screenshot%20pt1.png) | pfSense main dashboard |
| [pfSense Dashboard pt2](screenshots/pfSense%20Screenshot%20pt2.png) | pfSense system info |

### Week 2 - Attack & Defense
| Screenshot | Description |
|------------|-------------|
| [Snort Ubuntu Alerts](screenshots/Snort%20Ubuntu%20Alerts%20pt1.png) | Snort detecting Ubuntu attacks |
| [Snort Nmap pt1](screenshots/Snort%20nmap%20pt1.png) | Nmap scan detected by Snort |
| [Snort Nmap pt2](screenshots/Snort%20nmap%20pt2.png) | Nmap scan results continued |
| [Snort Nmap pt3](screenshots/Snort%20nmap%20pt3.png) | Nmap scan results continued |
| [Snort Results pt1](screenshots/Snort%20results%20pt1.png) | Snort alert results |
| [Snort Results pt2](screenshots/Snort%20results%20pt2.png) | Snort alert results continued |
| [Ubuntu Scan pt1](screenshots/Ubuntu%20Scan%20Detailed%20pt1.png) | Detailed Ubuntu vulnerability scan |
| [Ubuntu Scan pt2](screenshots/Ubuntu%20Scan%20Detailed%20pt2.png) | Detailed Ubuntu vulnerability scan continued |

---

## 🚀 Setup Guide

### Prerequisites
- VirtualBox 7.0+
- 8GB RAM minimum (16GB recommended)
- 100GB free disk space
- Stable internet connection

### Network Adapter Configuration

pfSense Adapter 1 (WAN)  : NAT
pfSense Adapter 2 (LAN)  : Host-only Adapter #2
pfSense Adapter 3 (OPT1) : Host-only Adapter #3
Kali Adapter 1           : Host-only Adapter #2
Ubuntu Adapter 1         : Host-only Adapter #3

### pfSense Interface Configuration

WAN  (em0): 10.0.2.15/24  (NAT)
LAN  (em1): 192.168.1.1/24
OPT1 (em2): 192.168.2.1/24
---

## 📚 Skills Demonstrated

### CompTIA Network+ Applied
- ✅ Network segmentation and architecture
- ✅ IP addressing and subnetting
- ✅ DHCP server configuration
- ✅ Firewall and routing concepts
- ✅ NAT configuration
- ✅ Network troubleshooting

### CompTIA Security+ Applied
- ✅ Defense in depth architecture
- ✅ DMZ implementation
- ✅ IDS/IPS configuration and monitoring
- ✅ Penetration testing methodology
- ✅ Vulnerability assessment
- ✅ Incident detection and response
- ✅ Security zone segmentation

---

## 🎯 Real-World Applications

This lab directly mirrors security architectures used by:
- **Defense contractors** (Lockheed Martin, Northrop Grumman)
  protecting classified networks with DMZ segmentation
- **SOC environments** using Snort for real-time threat detection
- **Red team/Blue team** exercises in enterprise environments

---

## 📅 Project Timeline

| Week | Focus | Status |
|------|-------|--------|
| Week 1 | Foundation - pfSense + Kali setup | ✅ Complete |
| Week 2 | IDS/IPS + Penetration Testing | ✅ Complete |
| Week 3 | Advanced Attacks + Incident Response | 🔄 In Progress |
| Week 4 | Logging + Security Audit Report | 📋 Planned |

---

## 👤 Author

**Logan Stacy**
- 🎓 UCF Computer Engineering (BS/MS Accelerated - ISML Track)
- 🔐 CompTIA Security+ Certified
- 🌐 CompTIA Network+ Certified
- 🏆 Top 15 Statewide - OCPS Cyber Challenge CTF
- 📧 [LinkedIn](https://linkedin.com/in/logan-stacy)
- 💻 [GitHub](https://github.com/lo067291)
