# 🕵️‍♂️ TryHackMe: Investigating Windows

**Room:** [Investigating Windows](https://tryhackme.com/room/investigatingwindows)  
**Category:** Digital Forensics & Incident Response  
**Level:** Beginner-Friendly  
**Status:** ✅ Completed

---

## 🧰 Tools I Used

- **FTK Imager** – To mount and explore the `.vhd` disk image
- **Autopsy** – To analyze browser history and file activity
- **RegRipper** – To extract and review Windows registry data
- **Windows Event Viewer / Event Logs** – To find login and execution events
- **Command Prompt / PowerShell** – For basic navigation and inspection

---

## 🧠 What I Learned

- How to investigate a Windows machine using forensic tools
- How to identify a downloaded malicious file and its execution
- How malware can maintain persistence using registry keys and services
- How to use Windows event logs to track user activity
- How to correlate data from the registry, logs, and file system

---

## 🔎 Case Summary

| Detail | Finding |
|--------|---------|
| **User** | Brandon |
| **Downloaded File** | `crackme.zip` from `http://mysoftwarecompany.com` |
| **Executed Program** | `CrackMe.exe` |
| **Persistence Method** | Registry Run key & Windows Service |
| **Service Name** | `CrackMeService` |
| **Service Location** | `C:\Users\Brandon\AppData\Local\CrackMeService\service.exe` |
| **Logon Event** | ID `4624` – Type 2 (Interactive) |
| **Execution Time** | `2021-02-24 15:42:18 UTC` |

---

## 📌 Where I Can Use This

- **Incident Response** – To analyze compromised Windows endpoints
- **Digital Forensics** – To investigate malware infections or user behavior
- **Security Operations** – To detect persistence methods and threats
- **Learning & Practice** – A good foundation for blue team and DFIR roles

---

## ✅ Final Thoughts

This room was a great introduction to Windows forensic investigation. It showed me how to follow the steps of a malware infection and identify persistence techniques using real system data. It also improved my ability to use forensic tools in a structured investigation.

---

📁 This write-up is part of my ongoing journey on TryHackMe. You can follow all my progress and upcoming modules on my profile:
🔗 https://tryhackme.com/p/PallaviKathait