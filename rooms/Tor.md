🧭 TryHackMe: Tor Room — Progress & Learning Documentation

Room Title: (https://tryhackme.com/room/torforbeginners)Tor (TryHackMe)
Platform: TryHackMe
Difficulty: Beginner
Category: Privacy · Anonymity · Reconnaissance (Tor / Onion Routing)
Goal: Learn how the Tor network works, route traffic through Tor (including with proxychains), use the Tor Browser safely, and understand basic OPSEC/responsible behavior while using Tor.

✅ Room Completion Summary

I completed every unit in the Tor room with hands-on configuration and verification.


Overview

Tor (The Onion Router) is a privacy network designed to anonymize internet traffic by routing it through multiple volunteer-operated relays and encrypting it in layers. This room teaches how Tor works, how to route traffic through Tor from command-line tools using proxychains, how to use the Tor Browser, and what operational safety concerns to watch for.

Unit 1 - Tor (What is Tor & How it Works)
What I Did

Reviewed Tor architecture (entry/guard, middle, exit nodes).

Observed Tor daemon behavior and circuit creation.

Inspected torrc configuration for common options.

Key Takeaways

Onion routing: Traffic is encrypted in layers and routed through at least three nodes; each node only knows its predecessor and successor.

Crawling vs. indexing analogy not relevant here — focus: Tor provides network-layer anonymity.

Exit node visibility: Data leaving the Tor network is visible to the exit node unless end-to-end encryption (HTTPS) is used.

Anonymity limits: Tor reduces linkability of your IP to web activity but misconfigurations, browser plugins, or logging in to identifiable accounts can deanonymize you.

Practical Application

Start/stop Tor service and inspect logs:

```
# On many Linux distros
sudo systemctl start tor
sudo journalctl -u tor -f
```

Check torrc (common locations: /etc/tor/torrc):

```
# Example lines
SocksPort 9050
ControlPort 9051
```

Unit 2 - Proxychains
What I Did

Installed proxychains (or proxychains-ng) and configured it to use Tor's SOCKS proxy.

Used proxychains to route CLI tools through Tor and verified the exit IP.

Key Takeaways

proxychains forces supported CLI programs to use a specified proxy (SOCKS5/HTTP).

Beware of tools that perform DNS resolution locally — DNS leaks can reveal your real IP.

Some network tools (certain nmap scans) may not work or will leak without careful configuration.

Practical Application (Examples)

Add Tor's SOCKS proxy to proxychains.conf:

```
[ProxyList]
# socks5  <ip>    <port>
socks5  127.0.0.1 9050
```

Verify routing through Tor:

```
proxychains curl https://check.torproject.org
proxychains curl https://ifconfig.me
```

Confirm output shows a Tor exit IP (not your real IP).

Unit 3 - Tor Browser
What I Did

Installed Tor Browser (Windows / macOS / Linux).

Started Tor Browser and set privacy/security slider to Safer (Level 2).

Visited a .onion site to validate functionality.

Key Takeaways

Tor Browser is a hardened Firefox-based browser that routes all traffic through Tor and reduces fingerprinting.

Use Tor Browser for .onion sites and general traffic you want anonymized.

The security slider reduces certain web features (JavaScript, media) to improve safety. Safer is a good balance of security and usability for learning labs.

Practical Application / Commands

Launch Tor Browser (linux example):

```
./start-tor-browser.desktop
```

Set Security Level: Shield icon → Security Settings → Safer.

.onion sites only resolve through Tor Browser or when properly routed through Tor SOCKS proxy.

Room Question Example

```
Q: What is the search engine at this onion address:
https://duckduckgogg42xjoc72x3sjasowoarfbgcmvfimaftt6twagswzczad.onion/
A: DuckDuckGo
```

Ethical & Safety Notes

Use Tor responsibly and legally. Tor is for privacy and legitimate research — do not use it to perform illegal actions.

Avoid logging into accounts in Tor Browser that can tie you to your identity unless you intentionally need to.

Prefer HTTPS to protect content from exit-node eavesdroppers.

Be aware of operational security (OPSEC) — browser plugins, downloadable files opened outside Tor, and device-level identifiers can deanonymize you.

Tools & Resources Used

TryHackMe Tor room content and labs

Tor Browser (official package)

Tor daemon (tor) — OS package/service

proxychains / proxychains-ng

CLI tools: curl, nc, nmap (use with caution)

Tor Project documentation (concepts and best practices)

Final Reflections

Completing the Tor room provided practical competence in:

Explaining onion routing and Tor circuit formation.

Configuring proxychains to route CLI tools through Tor and verifying routing.

Installing and hardening Tor Browser, and safely accessing .onion sites.

Understanding limitations and risks (DNS leaks, exit-node visibility, OPSEC mistakes).

Experience gained: Practical Tor setup, SOCKS proxying of CLI tools, safe Tor Browser usage, and a basic threat model for Tor — valuable for privacy-aware reconnaissance and safe research on the Tor network.