# 🛡️ Pyramid of Pain (https://tryhackme.com/room/pyramidofpainax)

The **Pyramid of Pain** is a threat intelligence model created by David Bianco that illustrates how difficult it is for adversaries to change different types of indicators of compromise (IOCs). The higher up the pyramid, the more disruptive your detection becomes.

This repository explains each layer of the pyramid and how you can use it to build a detection strategy that frustrates attackers and disrupts their campaigns.

---

## 📊 The Pyramid Layers

Each level represents an IOC type, ranked by how much it "hurts" the attacker when detected or blocked.

| Layer            | Difficulty     | Description |
|------------------|----------------|-------------|
| 🧊 **Hash Values**       | Trivial        | Cryptographic file hashes; easy to change. |
| 🌐 **IP Addresses**      | Easy           | C2 infrastructure IPs; frequently rotated. |
| 🏷️ **Domain Names**     | Simple         | Disposable, easily registered or changed. |
| 💻 **Host Artifacts**    | Annoying       | Registry keys, file paths, or mutexes left behind. |
| 📡 **Network Artifacts** | Annoying       | Beaconing patterns, HTTP headers, or unique C2 behaviors. |
| 🔧 **Tools**             | Challenging    | Frameworks and utilities like Mimikatz, Cobalt Strike. |
| ⚔️ **TTPs**              | Tough          | Adversary behavior and methods from frameworks like MITRE ATT&CK. |

---

## 🧩 Indicator Breakdown

### 🧊 Hash Values (Trivial)
- **What:** File hashes (MD5, SHA-1, SHA-256).
- **Example:** `44d88612fea8a8f36de82e1278abb02f` (EICAR test file)
- **Why It's Easy:** Attackers can modify a single byte to change the hash.
- **Detection Use:** Signature-based AV, IOC matching.
- **Adversary Impact:** 🚫 Very low

---

### 🌐 IP Addresses (Easy)
- **What:** IPs used for C2, phishing, or scanning.
- **Example:** `203.0.113.10`
- **Why It's Easy:** Attackers can quickly rotate IPs using dynamic hosting or proxies.
- **Detection Use:** Firewall blocks, network monitoring.
- **Adversary Impact:** 🛠️ Low

---

### 🏷️ Domain Names (Simple)
- **What:** Domains used in attacks (malware distribution, phishing).
- **Example:** `malicious-site.biz`
- **Why It's Simple:** Still easy to replace, but takes more setup than an IP.
- **Detection Use:** DNS filtering, SIEM alerts.
- **Adversary Impact:** 🔄 Moderate

---

### 💻 Host Artifacts (Annoying)
- **What:** Local machine traces like registry keys, files, mutexes.
- **Example:** `HKCU\Software\BadKey`, `C:\Temp\evil.exe`
- **Why It's Annoying:** Requires attacker to change malware behavior or rebuild.
- **Detection Use:** EDR agents, forensic analysis.
- **Adversary Impact:** 😒 Moderate to high

---

### 📡 Network Artifacts (Annoying)
- **What:** Unique network behaviors, beacon intervals, packet signatures.
- **Example:** HTTP GET requests every 60 seconds with specific user-agent.
- **Why It's Annoying:** Requires reconfiguring tools or C2 infrastructure.
- **Detection Use:** IDS, anomaly detection, traffic analysis.
- **Adversary Impact:** 📉 High

---

### 🔧 Tools (Challenging)
- **What:** Malware families or hacking frameworks used by adversaries.
- **Example:** Cobalt Strike, Mimikatz, Metasploit
- **Why It's Challenging:** Requires significant time to replace or rebuild tools.
- **Detection Use:** YARA, memory scanning, behavioral heuristics.
- **Adversary Impact:** 🔐 High

---

### ⚔️ TTPs (Tough)
- **What:** Tactics, Techniques, and Procedures — the attacker's playbook.
- **Example:** PowerShell abuse (`T1059.001`), phishing emails (`T1566`)
- **Why It's Tough:** Changing TTPs means rethinking the entire approach.
- **Detection Use:** MITRE ATT&CK mapping, behavioral analytics.
- **Adversary Impact:** 💣 Very high

---

## 🧠 How to Use This Model

### ✅ 1. Assess Detection Coverage
- Map your existing detections to each pyramid layer.
- Check if you’re stuck detecting only hashes/IPs.

### 🔼 2. Aim Higher
- Build detections for **behavioral patterns** (TTPs, tools, host/network artifacts).
- These are harder for adversaries to adapt to.

### 🔍 3. Threat Hunt Strategically
- Use the pyramid as a lens when threat hunting.
- Prioritize high-pain indicators to detect advanced threats.

### ⚔️ 4. Measure Impact
- The higher your detections are on the pyramid, the more time and effort the attacker must spend to evade you.

---

## 🏁 Conclusion

The **Pyramid of Pain** helps defenders understand where they’re hurting attackers — and where they’re just playing whack-a-mole. Focus on the **upper layers** (tools and TTPs) to truly disrupt adversaries and reduce their chance of success.

> Don't just detect. Disrupt.

---

## 📚 Resources

- [📄 Original Blog Post – David Bianco](https://detect-respond.blogspot.com/2013/03/the-pyramid-of-pain.html)
- [🔗 MITRE ATT&CK Framework](https://attack.mitre.org/)
- [🧪 YARA Rules Documentation](https://virustotal.github.io/yara/)
- [🧰 Sigma Rules (SIEM Detection Patterns)](https://github.com/SigmaHQ/sigma)
- [🎓 TryHackMe – Threat Intelligence Room](https://tryhackme.com/room/threatintel)

---

## 🛠️ Contributions

PRs welcome! Feel free to contribute examples, visuals, or detection rules that align with the Pyramid of Pain model.

📁 This write-up is part of my ongoing journey on TryHackMe. You can follow all my progress and upcoming modules on my profile:
🔗 https://tryhackme.com/p/PallaviKathait