# 🕵️ TryHackMe: Google Dorking Room – Progress & Learning Documentation

## 🗂️ Overview

- **Room Title:** Google Dorking (https://tryhackme.com/room/googledorking) 
- **Platform:** [TryHackMe](https://tryhackme.com/)  
- **Difficulty:** Beginner  
- **Category:** OSINT (Open-Source Intelligence), Reconnaissance  
- **Goal:** Understand how search engines work, how websites interact with crawlers, and how attackers use advanced Google search techniques (a.k.a. Google Dorking) to find sensitive, misconfigured, or exposed data online.

This room focuses on search engine internals, web crawling behavior, how content is indexed, and how to uncover unintentionally public information using advanced Google queries.

---

## ✅ Room Completion Summary

I approached each task in this room methodically, using hands-on practice with external tools like online robots.txt viewers, sitemap explorers, and Google Dork query crafting. Below is a detailed explanation of each task, the concept covered, and the real-world skills I developed.

---

## 🕸️ Task 2: Let's Learn About Crawlers

### 🔍 What I Did:
- Learned how search engine bots crawl web pages.
- Explored how crawlers collect information for indexing.
- Investigated `user-agent` strings used by bots like `Googlebot`, `msnbot`, and others.

### 🧠 Key Takeaways:
- **Web Crawlers (Spiders):** Automated programs that browse the web systematically.
- **Crawling vs Indexing:** Crawling is discovering pages; indexing is storing and categorizing them.
- **Bot Identification:** Bots identify themselves with user-agents like:
  - `Googlebot` for Google
  - `msnbot` for Bing

### 🛠 Practical Application:
- Checked my browser’s developer tools to see how pages reference robots.txt and sitemaps.
- Used headers in online tools to inspect user-agent strings of bots.

---

## 📈 Task 3: Search Engine Optimization (SEO)

### 🔍 What I Did:
- Reviewed how meta tags, content structure, and site responsiveness influence visibility in search results.
- Used SEO Site Checkup tools to evaluate SEO performance on various URLs.

### 🧠 Key Takeaways:
- **Meta Tags:** Define how a page appears in search results.
  - `<title>`: Page title shown in results.
  - `<meta name="description">`: Summary shown under the title.
- **Keyword Optimization:** Search engines rely heavily on relevant, structured content.
- **Responsiveness Matters:** Mobile-friendliness affects SEO rankings.

### 🛠 Practical Application:
- Ran SEO checks on sample sites using [SEO Site Checkup](https://seositecheckup.com/).
- Learned how attackers use poor SEO practices to identify under-maintained or vulnerable pages.

---

## 🤖 Task 4: Robots.txt

### 🔍 What I Did:
- Studied how `robots.txt` works to control crawler behavior.
- Learned the syntax for allowing and disallowing specific bots or paths.

### 🧠 Key Takeaways:
- File is located at the root of a domain: `https://example.com/robots.txt`
- **User-agent**: Defines which bot the rule applies to.
- **Disallow/Allow**: Specifies directories or files that bots can or cannot access.

### 📝 Examples:
```plaintext
User-agent: *
Disallow: /admin/

User-agent: Googlebot
Disallow: /confidential/

🚨 Important Insight:
Many websites unintentionally list sensitive paths in robots.txt, which attackers can manually review even though crawlers may avoid them.

🗺️ Task 5: Sitemaps
🔍 What I Did:
Explored how sitemaps help crawlers understand a site's structure.

Identified different sitemap formats (XML, image/video sitemaps).

🧠 Key Takeaways:
Sitemap.xml: Lists URLs of a site for search engines to index.

Often referenced in robots.txt like:

plaintext
Sitemap: https://example.com/sitemap.xml
Can include metadata about how often a page changes and its importance.

🛠 Practical Application:
Accessed real sitemaps on various domains (/sitemap.xml).

Analyzed structure and discovered endpoints not visible from the homepage.

🔍 Task 6: What is Google Dorking?
🔍 What I Did:
Practiced crafting advanced Google search queries (Google Dorks).

Used operators like intitle:, site:, filetype: to uncover specific content.

🧠 Key Takeaways:
Google Dorking = Using search operators to extract data from indexed pages.

Common operators:

site:example.com: Limits results to a specific domain.

intitle:"login": Pages with “login” in the title.

filetype:pdf: Finds PDF files.

🔐 Ethical Hacking Note:
Google Dorking is widely used during OSINT and reconnaissance phases to find misconfigured services, open directories, exposed credentials, or sensitive files.

🛠 Real Dorking Examples I Tried:
plaintext
site:gov.uk "confidential"
intitle:"index of /" password
filetype:xls intext:"username"
These revealed exposed files, improperly secured directories, and login portals — all indexed by Google.

🧠 Final Reflections
Completing the Google Dorking room significantly enhanced my understanding of:

How search engines interact with websites.

Methods to guide or restrict crawlers using robots.txt and sitemaps.

How websites can accidentally expose sensitive data through misconfigurations.

The power of advanced search operators for reconnaissance in ethical hacking.

I now understand how to use search engines as reconnaissance tools, a critical phase in penetration testing and OSINT investigations.

🛠 Tools and Resources Used
TryHackMe Room: Google Dorking

SEO Site Checkup

Google Search Operators Reference

Online robots.txt viewers and sitemap explorers

My browser's Developer Tools (Network & Console tabs)

Experience Gained: Solid foundation in search engine behavior, reconnaissance, and passive OSINT techniques.

