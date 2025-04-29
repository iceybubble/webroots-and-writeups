# 🌐 World Wide Web Badge — TryHackMe

> 🏅 Badge earned after completing the [How the Web Works](https://tryhackme.com/module/how-the-web-works) module  
> 📆 Date: March 20, 2025  
> 🧭 Module: https://tryhackme.com/module/how-the-web-works path on TryHackMe

---

## 📖 Overview

This write-up covers what I learned while completing the "How the Web Works" module. It gave me a solid understanding of how websites and the internet function on a technical level. It’s easy to take the internet for granted — we type in a URL and expect everything to just work — but this module broke it down piece by piece, and that made things click for me.

To become a better hacker it's vital to understand the underlying functions of the world wide web and what makes it work.

---

## 🧠 Key Concepts 

### 🕸️ DNS (Domain Name System)

Before we ever reach a website, our computer needs to figure out where it lives — that’s where DNS comes in. I learned how domain names are translated into IP addresses through DNS lookups, and how that sets everything else in motion.

---

### 🌍 HTTP & HTTPS

The module walked through how **HTTP** (and its secure version **HTTPS**) work under the hood. These protocols handle communication between a browser and a web server — things like:
-Methods like GET, POST, PUT, and DELETE — each serving a different purpose in data exchange.

-Status codes, such as:

-200 OK (success)

-301 Moved Permanently (redirect)

-403 Forbidden and 404 Not Found (errors)

-Headers that carry metadata about the request or response.

-Content types, which define what kind of data is being sent (HTML, JSON, etc.)

-Understanding how these pieces interact gave me a much clearer view of what’s happening behind the scenes of every webpage I load.

---

### How Websites Work

-To exploit a website, you first need to know how they are created.This part covered:

-Static vs dynamic content

-Frontend and backend technologies

-The flow of data between a user's browser and the backend server

-It reinforced the idea that every click, every form, every login is backed by logic and communication between components.

---

### 💻 Client-Server Model

I’d heard the term before, but this module made it click. The client (your browser) sends a request, and the server processes it, then sends a response. It’s basic, but also everything. Once I saw the flow laid out — request → server processes → response — it became easier to conceptualize web vulnerabilities like injections or improper access controls.

---


## 🧪 Practical Stuff

### ➤ Sending a Simple Request

```bash
curl http://example.com
This fetches the HTML content — kind of like viewing the raw page source.


➤ Viewing HTTP Headers

bash
curl -I http://example.com
This shows the response headers only. I saw stuff like server type, content type, and response codes.


➤ Simulating a POST 

bash
curl -X POST -d "username=admin&password=secret" http://example.com/login
Got hands-on with how form data gets sent to a server.


➤ Using Telnet to Build Raw Requests

bash
telnet example.com 80
Then manually sent:

vbnet
GET / HTTP/1.1
Host: example.com
It was wild to actually see the raw response come back without a browser involved — definitely helped me visualize the request/response cycle.


🔧 Tools I Used

curl – great for testing requests straight from the terminal

telnet – a bit old-school, but helpful to manually test HTTP

Browser DevTools – used these to analyze network activity and headers

🔍 What I Took Away From This

Everything on the web is built around communication between clients and servers.

DNS is the first step in every web request, and knowing how it works clears up a lot of "internet magic".

HTTP might be simple, but understanding it deeply makes a huge difference — especially when it comes to web security.

🚀 Next Up

Now that I have the basics of how the web actually functions, I’m planning to dig into:

Web application vulnerabilities (XSS, SQLi, CSRF)

Tools like Burp Suite

Practical web hacking labs

📁 This write-up is part of my ongoing journey on TryHackMe. You can follow all my progress and upcoming modules on my profile:
🔗 https://tryhackme.com/p/PallaviKathait





