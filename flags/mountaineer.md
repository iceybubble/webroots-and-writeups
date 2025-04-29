# 🏔️ Mountaineer — TryHackMe Room Write-Up

> 🏁 Room: [Mountaineer](https://tryhackme.com/room/mountaineerlinux)  
> 📆 Date Completed: March 17, 2025  
> 🎯 Flags Captured: 2 (User + Root)

---

🧭 Objective
The goal is to escalate privileges from a low-privileged user to root by exploiting various vulnerabilities and misconfigurations on a Linux-based system.

---

## 🧭 Overview

The Mountaineer room was focused on Linux enumeration and privilege escalation. It dropped me into a fairly simple environment, but required a bit of digging to find misconfigurations and vulnerable paths to privilege escalation. It was a great way to apply what I’ve been learning about system enumeration and Linux basics.

---

## 🧠 Enumeration & Initial Access

### 1. Nmap Scan

```bash
nmap -sV -Pn mountaineer.thm
Ports open:

22/tcp (SSH)

80/tcp (nginx HTTP server)

2. Web Recon
Found default nginx page.

Used gobuster to enumerate directories.

bash
gobuster dir -u http://mountaineer.thm -w /usr/share/wordlists/dirb/common.txt
Discovered /wordpress and /images.

3. Local File Inclusion (LFI)
bash
curl "http://mountaineer.thm/wordpress/images../../etc/passwd"
Confirmed LFI vulnerability.

🔍 Subdomain Enumeration
Discovered adminroundcubemail.mountaineer.thm from nginx config.

Added it to /etc/hosts.

📬 Webmail Access
Roundcube login found on subdomain.

Used credentials from a hint in the LFI:
k2:k2

Found emails mentioning:

Password reuse

Leaked credentials: th3_tall3st_password_in_th3_world

🔐 WordPress Exploitation
Logged in as k2 to WordPress at /wordpress/wp-admin.

Vulnerable plugin found: Modern Events Calendar v5.16.2

Used known RCE exploit to get reverse shell as www-data.

🔼 Privilege Escalation
1. KeePass File
Found Backup.kdbx in /home/lhotse/.

Used keepass2john + john to crack it with custom wordlist (CUPP).

bash
keepass2john Backup.kdbx > hash.txt
john hash.txt --wordlist=cupp.txt
Found password for kangchenjunga.

2. Root Access
Switched to kangchenjunga, searched .bash_history.

Found command to read /root/root.txt.

🧰 Tools Used
nmap, gobuster, curl, telnet

keepass2john, john, CUPP

Browser DevTools

🏁 Summary
LFI → Webmail → WordPress RCE → KeePass Cracking → Root

Great example of chaining multiple misconfigurations.

Reinforces value of thorough enumeration and creative pivoting.

📁 Part of my TryHackMe journey:
🔗 https://tryhackme.com/p/PallaviKathait

