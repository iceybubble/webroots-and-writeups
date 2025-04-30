# 🛰️ TryHackMe: Shodan.io Room Completion

## 📚 Overview

This document summarizes my learning experience from completing the **Shodan.io** room on [TryHackMe](https://tryhackme.com/). Shodan is a search engine for internet-connected devices and services, often used in cybersecurity for reconnaissance, monitoring, and vulnerability discovery.

---

## 🧠 Skills Learned

### 🔍 Shodan Fundamentals
- Gained an understanding of Shodan's purpose and functionality.
- Learned how it indexes devices based on open ports, protocols, and banners.

### 📡 Advanced Search Filters
- Used filters like `port:`, `org:`, `country:`, `before:`, `after:`, `product:`, `version:` to narrow down results.
- Practiced combining multiple filters for precise targeting.

### 🧰 Banner Analysis & Fingerprinting
- Interpreted banners to identify software versions and services.
- Recognized indicators of vulnerable or misconfigured systems.

### 🌐 Exposed Device Discovery
- Discovered:
  - Open databases (e.g., MongoDB, Elasticsearch)
  - IoT devices (cameras, printers)
  - ICS/SCADA systems
  - Services like FTP, RDP, and Telnet

### 🔧 Practical Reconnaissance
- Practiced non-intrusive reconnaissance using publicly indexed data.
- Mapped external attack surfaces of real-world organizations.

---

## 💻 Tools & Commands Practiced

- **Shodan Web Interface**: Manual search and filtering
- **Shodan CLI**:
  ```bash
  shodan search apache
  shodan host [IP]
  shodan stats apache --facets country


🚀 Real-World Applications

Use Case	                                  Description
🛡️ Blue Team	                 Identify exposed assets, monitor external risks
🔓 Red Team / Pentesters	    Pre-engagement recon, identify exploitable services
🧠 CTF/Practice             	Passive info gathering, fingerprinting
🏢 Enterprise Security	        Asset discovery, third-party risk analysis
🔍 Bug Bounty	                Locate exposed endpoints and misconfigurations

📌 Conclusion
Shodan is a powerful tool that provides insight into exposed devices and services on the internet. Through this room, I gained critical OSINT and reconnaissance skills useful in red teaming, blue teaming, and real-world cybersecurity operations.

📁 This write-up is part of my ongoing journey on TryHackMe. You can follow all my progress and upcoming modules on my profile:
🔗 https://tryhackme.com/p/PallaviKathait