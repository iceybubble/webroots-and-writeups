# 🔐 TryHackMe: Unified Kill Chain (https://tryhackme.com/room/unifiedkillchain)

## 🧠 What is the Unified Kill Chain?

The Unified Kill Chain is a cybersecurity model that explains how attackers plan and carry out their attacks from start to finish. It combines parts of two other popular models—MITRE ATT&CK and the Cyber Kill Chain—to give a full picture of the entire attack process.

This model helps defenders understand each step an attacker might take, so they can better detect, stop, and respond to threats.

---

## 📚 Room Overview

The [Unified Kill Chain](https://tryhackme.com/room/unifiedkillchain) room on TryHackMe is a mix of theory and hands-on exercises that walk you through the kill chain in action. It provides insight into how real-world attackers think, plan, and execute their attacks, giving you the chance to practice using offensive and defensive tools.

The room covers key concepts such as:
- Understanding each phase of the Unified Kill Chain
- Mapping attacker behavior to the framework
- Exploring common TTPs (Tactics, Techniques, and Procedures)
- Using real tools for exploitation and post-exploitation

---

## 🛠️ What I Learned

### 🔄 The Kill Chain Phases

1. **Preparation Phase (Pre-access)**
   - Reconnaissance: Gathering information about the target
   - Weaponization: Crafting malicious payloads

2. **Initial Access Phase**
   - Delivery: Sending the payload (e.g., phishing)
   - Exploitation: Gaining access through vulnerabilities

3. **Post-Access Phase**
   - Installation: Establishing persistence (e.g., backdoors)
   - Command & Control (C2): Remote interaction with the victim

4. **Objective Phase**
   - Actions on Objectives: Data theft, lateral movement, ransomware, etc.

### 🧰 Tools and Techniques Used
- **Metasploit** for payload creation and exploitation
- **PowerShell & Windows Commands** for enumeration and privilege escalation
- **Empire** and other C2 frameworks for post-exploitation
- **Manual techniques** for lateral movement and persistence

### 🔐 Defensive Insight
Throughout the room, I also explored detection methods and defense strategies for each phase, such as:
- Monitoring suspicious behavior in logs
- Implementing network segmentation
- Using EDR tools to catch anomalies
- Least privilege enforcement and patch management

---

## ✅ Key Takeaways

- The **Unified Kill Chain** offers a complete picture of adversary behavior across the entire attack lifecycle.
- Mapping attacker activity to this model enhances **threat detection**, **incident response**, and **red/blue team operations**.
- Hands-on labs help reinforce theoretical knowledge by simulating real-world attack chains.
- Understanding attacker mindset improves your ability to defend systems proactively—not just reactively.

---

## 📂 Useful Resources

- 📘 [Unified Kill Chain - GitHub](https://github.com/PaulPols/Unified-Kill-Chain)  
- 🔗 [MITRE ATT&CK Framework](https://attack.mitre.org/)  
- 🔐 [Lockheed Martin Cyber Kill Chain](https://www.lockheedmartin.com/en-us/capabilities/cyber/cyber-kill-chain.html)  
- 🎓 [TryHackMe Room](https://tryhackme.com/room/unifiedkillchain)

---

## 🙌 Final Thoughts

This room is a must-do for anyone looking to understand how attackers operate in a structured and strategic way. It helps bridge the gap between theory and practical cybersecurity skills. Highly recommended for SOC analysts, red teamers, and anyone diving deeper into threat modeling and incident response.

---

⚠️ Disclaimer: This write-up is for educational purposes and ethical use only. All activities were performed in a controlled environment on TryHackMe.

---

📁 This write-up is part of my ongoing journey on TryHackMe. You can follow all my progress and upcoming modules on my profile:
🔗 https://tryhackme.com/p/PallaviKathait
