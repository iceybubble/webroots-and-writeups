# 🕸️ TryHackMe: HTTP in Detail (https://tryhackme.com/room/httpindetail)– Badge Earned!

> ✅ Completed the **HTTP in Detail** room on [TryHackMe](https://tryhackme.com), earning the **Webbed** badge!  
> 📚 This room was all about understanding how the web works under the hood — focusing on HTTP(S), requests/responses, methods, headers, cookies, and tools for making and analyzing HTTP traffic.

---

## 🧠 What I Learned

### 🌍 1. HTTP & HTTPS Basics
- **HTTP (HyperText Transfer Protocol):** A stateless protocol used to transmit data between clients and servers.
- **HTTPS:** The secure version of HTTP, using **TLS/SSL encryption** to protect data in transit.

---

### 📤 2. HTTP Request Structure
An HTTP request typically contains:
- **Method** (e.g. `GET`, `POST`)
- **URL/Path**
- **Headers** (metadata like `User-Agent`, `Authorization`)
- **Body** (for methods like `POST` or `PUT`)

Example:
GET /index.html HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0


---

### 📥 3. HTTP Response Structure
A server responds with:
- **Status Code** (e.g. `200 OK`, `404 Not Found`)
- **Headers** (e.g. `Content-Type`, `Set-Cookie`)
- **Body** (e.g. HTML, JSON, images)

---

### 🚦 4. Status Codes Breakdown
| Code Type | Description | Example |
|-----------|-------------|---------|
| `1xx`     | Informational | `100 Continue` |
| `2xx`     | Success       | `200 OK`, `201 Created` |
| `3xx`     | Redirection   | `301 Moved`, `302 Found` |
| `4xx`     | Client Error  | `400 Bad Request`, `404 Not Found` |
| `5xx`     | Server Error  | `500 Internal Server Error`, `502 Bad Gateway` |

---

### 📬 5. Common HTTP Methods
| Method | Use Case              |
|--------|-----------------------|
| `GET`  | Retrieve data         |
| `POST` | Submit data           |
| `PUT`  | Update/replace data   |
| `DELETE` | Remove data        |
| `HEAD`, `OPTIONS`, `PATCH` | Other control and update methods |

---

### 🧾 6. Headers
Headers carry metadata in both requests and responses:
- `Content-Type`: Type of data (`text/html`, `application/json`)
- `User-Agent`: Info about client/browser
- `Authorization`: Tokens or credentials
- `Set-Cookie`: Stores data client-side

---

### 🍪 7. Cookies
- Small pieces of data stored on the client by the server
- Useful for **sessions**, **preferences**, **auth**
- Sent with every request via `Cookie` header

---

### 🛠️ 8. Making & Inspecting Requests
**Tools covered:**
- `curl` & `wget` for CLI-based requests
- **Browser DevTools** (Network tab) for live analysis
- **Burp Suite** for intercepting and modifying traffic

Example using `curl`:
```bash
curl -X POST https://example.com/login -d "username=admin&password=1234"

🏆 Badge Earned: Webbed

📌 Final Thoughts
This room gave me a solid foundation in web fundamentals, especially useful for:

Web app hacking

CTFs

Bug bounty hunting

Backend development

📁 This doc is now part of my GitHub learning journal. More rooms and writeups coming soon!
