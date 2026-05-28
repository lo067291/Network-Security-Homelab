# Network-Security-Homelab
Enterprise-grade network security lab simulating defense infrastructure with pfSense firewall, Kali Linux attack machine, and network segmentation

# Enterprise Network Security Homelab

![Status](https://img.shields.io/badge/Status-Active-green)
![pfSense](https://img.shields.io/badge/Firewall-pfSense-blue)
![Kali](https://img.shields.io/badge/Attack-Kali_Linux-red)

## 🎯 Project Overview
Enterprise-grade network security lab simulating classified defense infrastructure with multiple security zones, firewall segmentation, and attack/defense capabilities. Built to demonstrate practical application of CompTIA Network+ and Security+ knowledge in a real-world environment.

---

## 🏗️ Network Architecture
INTERNET
                   |
          [WAN: em0 - NAT]
                   |
          ┌────────────────┐
          │  pfSense       │
          │  Firewall      │
          │  192.168.x.1   │
          └────────────────┘
                   |
      ┌────────────┴────────────┐
      │                         │
      [LAN: em1]                 [OPT1: em2]
192.168.1.0/24             192.168.2.0/24
Internal Network                DMZ
│                         │
[Future: Ubuntu]          [Kali Linux]
File/Web Server           Attack Machine

---

## 🔧 Technologies Used

| Technology | Purpose | Version |
|------------|---------|---------|
| pfSense | Firewall/Router | v1.2 RELEASE |
| Kali Linux | Penetration Testing | 2024.x |
| VirtualBox | Virtualization | 7.0 |
| pfSense WebGUI | Firewall Management | - |

---

## 🔒 Security Zones

### WAN (Internet Facing)
- NAT interface connecting to internet
- All inbound traffic blocked by default
- Only established connections allowed back in

### DMZ - 192.168.2.0/24
- Houses attack machine (Kali Linux)
- Limited access to internal network
- Simulates public-facing services zone

### Internal Network - 192.168.1.0/24
- Protected internal zone
- Houses administrative systems
- Restricted access from DMZ

---

## 📊 Current Lab Capabilities

### ✅ Completed (Week 1)
- pfSense firewall installation and configuration
- Network segmentation (3 security zones)
- DHCP configuration for all zones
- Web-based firewall management (WebGUI)
- Kali Linux attack machine deployment
- Network connectivity verified between zones

### 🔄 In Progress (Week 2)
- Snort IDS/IPS configuration
- Advanced firewall rules
- VPN setup
- Ubuntu server deployment
- Attack simulation and logging

### 📋 Planned (Weeks 3-4)
- Penetration testing documentation
- Centralized logging (ELK Stack)
- Incident response procedures
- Full security audit report

---

## 🖥️ Lab Environment

| VM | OS | IP Address | Role | Network |
|----|-----|------------|------|---------|
| pfSense-Firewall | pfSense CE | 192.168.2.1 | Firewall/Router | All zones |
| Kali-Attack | Kali Linux | 192.168.2.10 | Attack Machine | DMZ |
| Ubuntu-Server | Ubuntu Server | TBD | Target Server | Internal |

---

## 📸 Screenshots
<img width="1692" height="877" alt="pfSense Screenshot pt1" src="https://github.com/user-attachments/assets/b5726a28-b295-4b15-ba07-0ba7b2fcd4e4" />
<img width="1692" height="881" alt="pfSense Screenshot pt2" src="https://github.com/user-attachments/assets/009b8fcb-46be-4cd1-a5fd-8349c1c5a6ed" />

---

## 🚀 Setup Guide

### Prerequisites
- VirtualBox 7.0+
- 8GB RAM minimum (16GB recommended)
- 100GB free disk space
- Stable internet connection

### Installation Steps

**1. Download Required ISOs:**
- pfSense: https://www.pfsense.org/download
- Kali Linux: https://www.kali.org/get-kali

**2. Create pfSense VM:**
Type: Linux (Other Linux 64-bit)
RAM: 2048 MB
Disk: 20 GB
Network Adapters: 3 (NAT, Internal-DMZ, Internal-LAN)

**3. Create Kali VM:**
Type: Linux (Debian 64-bit)
RAM: 2048 MB
Disk: 30 GB
Network: Internal Network (DMZ)

**4. Configure pfSense:**
WAN: em0 (NAT)
LAN: em1 (192.168.1.1/24)
OPT1/DMZ: em2 (192.168.2.1/24)

**5. Access WebGUI:**
URL: https://192.168.2.1
Username: admin
Password: [your password]

---

## 📚 Skills Demonstrated

### CompTIA Network+ Applied
- ✅ Network segmentation and architecture
- ✅ IP addressing and subnetting (192.168.x.0/24)
- ✅ DHCP server configuration
- ✅ Firewall and routing concepts
- ✅ NAT configuration
- ✅ Network troubleshooting

### CompTIA Security+ Applied
- ✅ Defense in depth architecture
- ✅ DMZ implementation
- ✅ Least privilege network access
- ✅ Security zone segmentation
- ✅ Firewall rule management
- ✅ Network monitoring

---

## 🎯 Real-World Applications

This lab directly mirrors security architectures used by:
- **Defense contractors** (Lockheed Martin, Northrop Grumman) protecting classified networks with DMZ segmentation
- **Enterprise networks** using pfSense for perimeter security
- **SOC environments** monitoring network traffic and threats

---

## 📅 Project Timeline

| Week | Focus | Status |
|------|-------|--------|
| Week 1 | Foundation - pfSense + Kali setup | ✅ Complete |
| Week 2 | IDS/IPS + Advanced firewall rules | 🔄 In Progress |
| Week 3 | Attack simulation + logging | 📋 Planned |
| Week 4 | Documentation + security report | 📋 Planned |

---

## 👤 Author

**Logan Stacy**
- 🎓 UCF Computer Engineering (BS/MS Accelerated - ISML Track)
- 🔐 CompTIA Security+ Certified
- 🌐 CompTIA Network+ Certified
- 🏆 Top 15 Statewide - OCPS Cyber Challenge CTF
- 📧 [LinkedIn](https://linkedin.com/in/logan-stacy)
- 💻 [GitHub](https://github.com/lo067291)
