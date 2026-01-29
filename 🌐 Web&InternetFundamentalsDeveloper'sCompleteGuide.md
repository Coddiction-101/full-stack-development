# 🌐 Web & Internet Fundamentals - Developer's Complete Guide

**For Full Stack Developers | Beginner to Advanced**

---

## 📋 Table of Contents
1. [Internet vs Web](#internet-vs-web)
2. [Client-Server Architecture](#client-server)
3. [Browser & Server Roles](#browser-server)
4. [DNS, IP, Domain, URL](#dns-ip-domain-url)
5. [HTTP/HTTPS](#http-https)
6. [Request Flow: Browser to Server](#request-flow)
7. [Essential Web Concepts](#essential-concepts)
8. [Common Misunderstandings](#misunderstandings)
9. [Interview Questions](#interview-questions)
10. [One-Page Cheat Sheet](#cheat-sheet)

---

## 🌍 Internet vs Web {#internet-vs-web}

### **What They Are:**

**Internet:**
- Global network of interconnected computers
- Physical infrastructure (cables, routers, servers)
- Enables data transmission between devices
- Exists since 1960s (ARPANET)

**Web (World Wide Web):**
- Service built ON TOP of the Internet
- Collection of websites and web pages
- Accessed via HTTP/HTTPS protocols
- Invented by Tim Berners-Lee in 1989

### **Key Difference:**
```
Internet = Roads & Highways (infrastructure)
Web      = Cars traveling on those roads (service)
```

**Analogy:**
```
Internet = Phone network
Web      = One app on your phone

Other services on Internet:
- Email (SMTP)
- File Transfer (FTP)
- Video calls (WebRTC)
- Messaging (XMPP)
```

### **Why Developers Must Know:**
- ✅ Internet = transport layer (TCP/IP)
- ✅ Web = application layer (HTTP, HTML, CSS, JS)
- ✅ You build for the Web, which runs on the Internet

### **Common Confusion:**
❌ "I have no Internet" → Actually means "I can't access the Web"  
✅ Internet is working (can ping servers), Web browser can't load pages

---

## 🖥️ Client-Server Architecture {#client-server}

### **What It Is:**
- **Model where two entities communicate:**
  - **Client:** Requests services (browser, mobile app)
  - **Server:** Provides services (web server, database)

### **How It Works:**
```
Client (Browser)  →  Request   →  Server (Web Server)
                 ←  Response  ←
```

### **Real-World Example:**
```
Restaurant Analogy:
Client = Customer (orders food)
Server = Waiter (brings food)
Kitchen = Backend server (prepares food)
Menu = API documentation
```

### **Types of Architecture:**

#### **1. Two-Tier (Client-Server)**
```
Browser ↔ Web Server (with database)
```
- Simple apps
- Direct connection
- Example: Small business websites

#### **2. Three-Tier**
```
Browser ↔ Web Server ↔ Database Server
         (Application)   (Data)
```
- Most modern web apps
- Separation of concerns
- Example: E-commerce sites

#### **3. N-Tier / Microservices**
```
Browser ↔ API Gateway ↔ Multiple Services
                        ├─ User Service
                        ├─ Payment Service
                        └─ Notification Service
```
- Large-scale applications
- Each service independent
- Example: Netflix, Amazon

### **Client Types:**

**Thin Client:**
- Minimal processing on client
- Heavy reliance on server
- Example: Web apps (Gmail, Google Docs)

**Thick Client:**
- Heavy processing on client
- Less server dependency
- Example: Desktop apps (Photoshop, VS Code)

**Hybrid:**
- Mix of both
- Example: Modern SPAs (React, Angular)

### **Why It Matters:**
- ✅ **Scalability:** Add more servers as users grow
- ✅ **Security:** Sensitive logic on server, not client
- ✅ **Maintenance:** Update server without touching clients
- ✅ **Resource Management:** Server handles heavy computation

### **Developer's Role:**
**Frontend Dev:** Build the client (React, Vue, HTML/CSS)  
**Backend Dev:** Build the server (Node.js, Django, Rails)  
**Full Stack:** Both client and server

---

## 🌐 Browser & Server Roles {#browser-server}

### **Browser (Client-Side)**

**What Browser Does:**
1. **Sends HTTP requests** to servers
2. **Receives HTML, CSS, JS** from server
3. **Renders web pages** (DOM + CSSOM → Render Tree)
4. **Executes JavaScript** (V8, SpiderMonkey engines)
5. **Stores data locally** (Cookies, LocalStorage, IndexedDB)
6. **Enforces security** (CORS, CSP, Same-Origin Policy)

**Browser Components:**
```
Browser
├─ UI (Address bar, buttons)
├─ Browser Engine (Rendering pipeline)
├─ JavaScript Engine (V8, SpiderMonkey)
├─ Networking (HTTP requests)
├─ Storage (Cookies, LocalStorage)
└─ Security (CORS, XSS protection)
```

**Popular Browsers & Engines:**
| Browser | Rendering Engine | JS Engine |
|---------|-----------------|-----------|
| Chrome | Blink | V8 |
| Firefox | Gecko | SpiderMonkey |
| Safari | WebKit | JavaScriptCore |
| Edge | Blink | V8 |

**What Runs in Browser:**
- ✅ HTML (structure)
- ✅ CSS (styling)
- ✅ JavaScript (interactivity)
- ✅ WebAssembly (high-performance)

**Browser Limitations:**
- ❌ Can't access file system (security)
- ❌ Can't make cross-origin requests (CORS)
- ❌ Limited to client-side logic
- ❌ User can inspect/modify code (DevTools)

---

### **Server (Server-Side)**

**What Server Does:**
1. **Listens for requests** on specific ports
2. **Processes business logic** (authentication, calculations)
3. **Queries databases** (fetch/save data)
4. **Generates responses** (HTML, JSON, XML)
5. **Enforces authentication** (JWT, sessions)
6. **Manages sessions** (track logged-in users)

**Server Components:**
```
Web Server
├─ HTTP Server (Apache, Nginx)
├─ Application Server (Node.js, Django, Rails)
├─ Database (MySQL, MongoDB, PostgreSQL)
├─ File Storage (S3, local files)
└─ Caching (Redis, Memcached)
```

**What Runs on Server:**
- ✅ Backend languages (Node.js, Python, Java, PHP)
- ✅ Database queries (SQL, MongoDB)
- ✅ Authentication logic (passwords, tokens)
- ✅ API endpoints (REST, GraphQL)
- ✅ File processing (images, PDFs)

**Server Advantages:**
- ✅ Secure (code not exposed to users)
- ✅ Access to databases
- ✅ Heavy computation (AI, video processing)
- ✅ Centralized logic (update once, affects all users)

**Common Server Ports:**
- `80` → HTTP
- `443` → HTTPS
- `3000` → Node.js dev server
- `8080` → Alternative HTTP
- `27017` → MongoDB
- `3306` → MySQL

---

### **Client vs Server: Who Does What?**

| Task | Client | Server | Why |
|------|--------|--------|-----|
| Validate email format | ✅ | ✅ | Client: UX, Server: Security |
| Check password strength | ✅ | ❌ | Quick feedback |
| Verify user exists | ❌ | ✅ | Database access |
| Calculate total price | ✅ | ✅ | Client: Preview, Server: Final |
| Store credit card | ❌ | ✅ | Security (PCI compliance) |
| Render HTML | ✅ | ✅* | Server: SSR, Client: CSR |
| Image compression | ❌ | ✅ | Heavy computation |

**Rule of Thumb:**
- **Client:** UI/UX, immediate feedback, light validation
- **Server:** Security, database access, business logic, final validation

---

## 🔍 DNS, IP, Domain, URL {#dns-ip-domain-url}

### **IP Address (Internet Protocol)**

**What It Is:**
- Unique identifier for devices on a network
- Like a phone number for computers

**Types:**

**IPv4:**
- Format: `192.168.1.1` (4 octets, 0-255)
- 32-bit (4 billion addresses)
- Running out of addresses

**IPv6:**
- Format: `2001:0db8:85a3:0000:0000:8a2e:0370:7334`
- 128-bit (340 undecillion addresses)
- Future of Internet

**Special IPs:**
- `127.0.0.1` → Localhost (your own computer)
- `0.0.0.0` → All interfaces (server listens on all IPs)
- `192.168.x.x` → Private network (home/office)
- `10.x.x.x` → Private network (large organizations)

**Public vs Private:**
- **Public IP:** Visible on Internet (assigned by ISP)
- **Private IP:** Only within local network (router assigns)

---

### **Domain Name**

**What It Is:**
- Human-readable address for websites
- Maps to IP address via DNS

**Structure:**
```
https://www.example.com
        │   │      │
        │   │      └─ TLD (Top-Level Domain)
        │   └──────── Second-Level Domain
        └──────────── Subdomain
```

**TLD Types:**
- `.com` → Commercial
- `.org` → Organization
- `.net` → Network
- `.edu` → Education
- `.gov` → Government
- `.io` → Tech startups (originally Indian Ocean)
- `.dev` → Developers (Google)
- `.ai` → AI companies (originally Anguilla)

**Subdomain Examples:**
- `www.example.com` → Main website
- `blog.example.com` → Blog
- `api.example.com` → API server
- `cdn.example.com` → Content Delivery Network

---

### **DNS (Domain Name System)**

**What It Is:**
- "Phone book of the Internet"
- Translates domain names → IP addresses
- Distributed database system

**How DNS Works:**
```
1. Browser checks cache
   ↓ (if not found)
2. Asks DNS Resolver (ISP)
   ↓ (if not found)
3. Root DNS Server
   ↓
4. TLD DNS Server (.com)
   ↓
5. Authoritative DNS Server
   ↓
6. Returns IP address
   ↓
7. Browser connects to IP
```

**DNS Record Types:**

| Type | Purpose | Example |
|------|---------|---------|
| A | IPv4 address | `93.184.216.34` |
| AAAA | IPv6 address | `2606:2800:220:1:...` |
| CNAME | Alias to another domain | `www` → `example.com` |
| MX | Mail server | `mail.example.com` |
| TXT | Text information | SPF, DKIM records |
| NS | Name server | `ns1.example.com` |

**DNS Caching:**
- **Browser Cache:** 5-30 minutes
- **OS Cache:** Hours
- **ISP Cache:** Days
- **TTL (Time To Live):** How long to cache

**Why DNS Matters:**
- ✅ No need to remember IP addresses
- ✅ Can change server IP without changing domain
- ✅ Load balancing (multiple IPs for one domain)
- ✅ CDN routing (serve from nearest server)

**Common DNS Issues:**
- **DNS Propagation:** Changes take 24-48 hours globally
- **DNS Poisoning:** Attacker changes DNS records
- **DNS Hijacking:** ISP redirects failed lookups

---

### **URL (Uniform Resource Locator)**

**What It Is:**
- Complete address to access a resource
- Contains all info to locate and retrieve content

**URL Structure:**
```
https://user:pass@www.example.com:443/path/to/page?key=value#section

│      │         │                │   │            │          │
│      │         │                │   │            │          └─ Fragment (anchor)
│      │         │                │   │            └──────────── Query String
│      │         │                │   └───────────────────────── Path
│      │         │                └───────────────────────────── Port
│      │         └────────────────────────────────────────────── Host
│      └──────────────────────────────────────────────────────── Credentials
└─────────────────────────────────────────────────────────────── Scheme/Protocol
```

**Components Explained:**

**1. Scheme/Protocol:**
- `http://` → Insecure
- `https://` → Secure (SSL/TLS)
- `ftp://` → File Transfer
- `ws://` / `wss://` → WebSocket

**2. Credentials (Deprecated):**
- `user:password@` → Avoid! Security risk
- Modern: Use headers/tokens

**3. Host:**
- Domain name or IP address
- `example.com` or `192.168.1.1`

**4. Port:**
- Default: `80` (HTTP), `443` (HTTPS)
- Custom: `:3000`, `:8080`
- Usually hidden if default

**5. Path:**
- `/products/shoes/nike`
- `/api/users/123`
- `/blog/2024/01/post`

**6. Query String:**
- `?search=laptop&sort=price&page=2`
- Key-value pairs
- Separated by `&`
- Visible in browser (not for sensitive data!)

**7. Fragment/Hash:**
- `#section-2`
- Client-side only (not sent to server)
- Used for anchor links, SPA routing

**URL Encoding:**
```javascript
// Spaces and special characters must be encoded
const search = "hello world & friends";
const encoded = encodeURIComponent(search);
// "hello%20world%20%26%20friends"

// Common encodings:
// Space → %20 or +
// & → %26
// ? → %3F
// = → %3D
```

---

## 🔒 HTTP/HTTPS {#http-https}

### **HTTP (Hypertext Transfer Protocol)**

**What It Is:**
- Protocol for transmitting web pages
- Stateless (each request independent)
- Request-response model

**HTTP Versions:**

| Version | Year | Features |
|---------|------|----------|
| HTTP/0.9 | 1991 | Only GET, no headers |
| HTTP/1.0 | 1996 | Headers, POST, status codes |
| HTTP/1.1 | 1997 | Persistent connections, chunked transfer |
| HTTP/2 | 2015 | Multiplexing, server push, binary |
| HTTP/3 | 2022 | QUIC, faster, more reliable |

---

### **HTTP Request Structure**

```
POST /api/users HTTP/1.1
Host: example.com
Content-Type: application/json
Authorization: Bearer abc123xyz
Cookie: session_id=xyz789
User-Agent: Mozilla/5.0

{"name": "John", "email": "john@example.com"}
```

**Components:**

**1. Request Line:**
- Method: `GET`, `POST`, `PUT`, `DELETE`
- Path: `/api/users`
- Version: `HTTP/1.1`

**2. Headers:**
- Metadata about request
- Key-value pairs

**3. Body (optional):**
- Data being sent
- JSON, FormData, XML

---

### **HTTP Methods**

| Method | Purpose | Has Body | Safe | Idempotent |
|--------|---------|----------|------|------------|
| GET | Retrieve data | No | ✅ | ✅ |
| POST | Create new resource | Yes | ❌ | ❌ |
| PUT | Update/Replace resource | Yes | ❌ | ✅ |
| PATCH | Partial update | Yes | ❌ | ❌ |
| DELETE | Remove resource | No | ❌ | ✅ |
| HEAD | Get headers only | No | ✅ | ✅ |
| OPTIONS | Check allowed methods | No | ✅ | ✅ |

**Safe:** Doesn't modify data  
**Idempotent:** Multiple identical requests = same result

**Examples:**
```javascript
// GET - Retrieve users
GET /api/users

// POST - Create user
POST /api/users
Body: {"name": "John", "email": "john@example.com"}

// PUT - Replace user
PUT /api/users/123
Body: {"name": "Jane", "email": "jane@example.com"}

// PATCH - Update email only
PATCH /api/users/123
Body: {"email": "newemail@example.com"}

// DELETE - Remove user
DELETE /api/users/123
```

---

### **HTTP Response Structure**

```
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 58
Set-Cookie: session_id=abc123; HttpOnly
Cache-Control: no-cache

{"id": 1, "name": "John", "email": "john@example.com"}
```

---

### **HTTP Status Codes**

**1xx - Informational:**
- `100 Continue` → Continue sending request
- `101 Switching Protocols` → WebSocket upgrade

**2xx - Success:**
- `200 OK` → Request successful
- `201 Created` → Resource created (POST)
- `204 No Content` → Success, no response body (DELETE)

**3xx - Redirection:**
- `301 Moved Permanently` → Resource moved (SEO: update links)
- `302 Found` → Temporary redirect
- `304 Not Modified` → Use cached version

**4xx - Client Errors:**
- `400 Bad Request` → Malformed request
- `401 Unauthorized` → Authentication required
- `403 Forbidden` → No permission
- `404 Not Found` → Resource doesn't exist
- `405 Method Not Allowed` → Wrong HTTP method
- `429 Too Many Requests` → Rate limited

**5xx - Server Errors:**
- `500 Internal Server Error` → Server crashed
- `502 Bad Gateway` → Proxy/gateway issue
- `503 Service Unavailable` → Server overloaded
- `504 Gateway Timeout` → Server took too long

**Developer's Rule:**
- `4xx` → Client's fault (fix request)
- `5xx` → Server's fault (fix backend)

---

### **Important HTTP Headers**

**Request Headers:**
```
Authorization: Bearer token123
Cookie: session_id=abc123
Content-Type: application/json
Accept: application/json
User-Agent: Mozilla/5.0
Referer: https://google.com
Origin: https://example.com
```

**Response Headers:**
```
Set-Cookie: session_id=xyz; HttpOnly; Secure
Content-Type: application/json
Cache-Control: max-age=3600
Access-Control-Allow-Origin: *
Location: /new-url (for redirects)
```

**Security Headers:**
```
Strict-Transport-Security: max-age=31536000
X-Content-Type-Options: nosniff
X-Frame-Options: DENY
Content-Security-Policy: default-src 'self'
```

---

### **HTTPS (HTTP Secure)**

**What It Is:**
- HTTP + SSL/TLS encryption
- Encrypted communication
- Data can't be read by middlemen

**How HTTPS Works:**
```
1. Browser requests HTTPS connection
2. Server sends SSL Certificate
3. Browser verifies certificate (CA check)
4. Browser & server establish encrypted connection (TLS handshake)
5. Data transmitted encrypted
```

**SSL/TLS Certificate:**
- Issued by Certificate Authority (CA)
- Contains: Domain name, Company info, Public key
- Types:
  - **Domain Validation (DV):** Basic (Let's Encrypt - Free)
  - **Organization Validation (OV):** Verified company
  - **Extended Validation (EV):** Highest trust (green bar)

**Why HTTPS Matters:**
- ✅ **Security:** Data encrypted
- ✅ **Trust:** Users trust padlock icon
- ✅ **SEO:** Google ranks HTTPS higher
- ✅ **Features:** PWA, geolocation need HTTPS
- ✅ **Compliance:** GDPR, PCI-DSS require it

**HTTP vs HTTPS:**
| Feature | HTTP | HTTPS |
|---------|------|-------|
| Port | 80 | 443 |
| Encryption | ❌ | ✅ |
| Speed | Faster | Slightly slower |
| SEO | Lower rank | Higher rank |
| Certificate | Not needed | Required |

---

## 🚀 Request Flow: Browser to Server {#request-flow}

### **Complete Journey of a Web Request**

```
1. User types URL → www.example.com
2. Browser checks cache
3. DNS Resolution
4. TCP Connection
5. TLS Handshake (HTTPS)
6. HTTP Request sent
7. Server processes request
8. HTTP Response returned
9. Browser renders page
10. Additional requests (CSS, JS, images)
```

---

### **Step-by-Step Breakdown:**

#### **Step 1: User Action**
```
User types: www.example.com
Browser adds: https:// (default)
Final URL: https://www.example.com
```

#### **Step 2: Browser Cache Check**
```
Browser checks:
1. Browser cache (5-30 min)
2. Service Worker cache
3. If found → skip to Step 9
```

#### **Step 3: DNS Resolution**
```
Browser → DNS Resolver → Root DNS → TLD DNS → Authoritative DNS
Returns: example.com = 93.184.216.34
Time: 20-120ms
```

#### **Step 4: TCP Connection (3-Way Handshake)**
```
Browser → SYN packet → Server
Server → SYN-ACK packet → Browser
Browser → ACK packet → Server
Connection established
Time: 30-100ms
```

#### **Step 5: TLS Handshake (HTTPS only)**
```
1. Browser → ClientHello (supported encryption)
2. Server → ServerHello + Certificate
3. Browser verifies certificate
4. Browser generates session key (encrypted with server's public key)
5. Encrypted connection established
Time: 50-200ms
```

#### **Step 6: HTTP Request Sent**
```
GET / HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0
Accept: text/html
Cookie: session_id=abc123
```

#### **Step 7: Server Processing**
```
1. Web server (Nginx/Apache) receives request
2. Routes to application server (Node.js/Django)
3. Application processes:
   - Check authentication
   - Query database
   - Generate response
4. Server prepares HTTP response
Time: 100-500ms (varies by logic)
```

#### **Step 8: HTTP Response Returned**
```
HTTP/1.1 200 OK
Content-Type: text/html
Content-Length: 1234
Set-Cookie: session_id=xyz

<!DOCTYPE html>
<html>...</html>
```

#### **Step 9: Browser Rendering**
```
1. Parse HTML → DOM tree
2. Parse CSS → CSSOM tree
3. Combine → Render tree
4. Layout (calculate positions)
5. Paint (draw pixels)
6. Composite layers
Time: 100-1000ms
```

#### **Step 10: Additional Requests**
```
Browser finds in HTML:
- <link href="style.css"> → GET request
- <script src="app.js"> → GET request
- <img src="logo.png"> → GET request

Each resource goes through Steps 6-9
```

---

### **Total Time Breakdown:**

```
DNS Lookup:        20-120ms
TCP Handshake:     30-100ms
TLS Handshake:     50-200ms
HTTP Request:      10-50ms
Server Processing: 100-500ms
HTTP Response:     10-50ms
Browser Rendering: 100-1000ms
─────────────────────────────
TOTAL:            320-2020ms (0.3-2 seconds)
```

**Optimization Opportunities:**
- ✅ DNS prefetching
- ✅ HTTP/2 multiplexing
- ✅ CDN (reduce latency)
- ✅ Caching
- ✅ Code splitting
- ✅ Lazy loading

---

### **Visual Diagram:**

```
┌─────────┐
│ Browser │
└────┬────┘
     │ 1. User types URL
     ▼
┌─────────────┐
│ DNS Lookup  │ → IP: 93.184.216.34
└─────┬───────┘
      │ 2. DNS Resolution
      ▼
┌──────────────┐
│ TCP Connect  │ → SYN, SYN-ACK, ACK
└──────┬───────┘
       │ 3. Establish connection
       ▼
┌──────────────┐
│ TLS Handshake│ → Secure connection (HTTPS)
└──────┬───────┘
       │ 4. Encrypted tunnel
       ▼
┌─────────────────┐
│ HTTP GET Request│ → GET /index.html
└────────┬────────┘
         │ 5. Send request
         ▼
    ┌────────┐
    │ Server │
    └────┬───┘
         │ 6. Process request
         │    - Check auth
         │    - Query database
         │    - Generate HTML
         ▼
┌──────────────────┐
│ HTTP Response    │ → 200 OK + HTML
└────────┬─────────┘
         │ 7. Send response
         ▼
┌─────────────────┐
│ Browser Renders │ → DOM + CSSOM → Paint
└─────────────────┘
```

---

## 💡 Essential Web Concepts {#essential-concepts}

### **1. Same-Origin Policy (SOP)**

**What It Is:**
- Security feature in browsers
- Prevents scripts from one origin accessing data from another origin

**Origin = Protocol + Domain + Port**
```
https://example.com:443/page1
│      │          │       │
Protocol Domain   Port    Path

Same origin:
✅ https://example.com/page2 (same everything)
✅ https://example.com:443/api (default port)

Different origin:
❌ http://example.com (different protocol)
❌ https://api.example.com (different subdomain)
❌ https://example.com:8080 (different port)
```

**Why It Exists:**
- Prevent malicious websites from accessing your data
- Example: Evil.com can't read your Gmail emails

**Impact on Developers:**
- AJAX requests to different origins blocked
- Solution: CORS (Cross-Origin Resource Sharing)

---

### **2. CORS (Cross-Origin Resource Sharing)**

**What It Is:**
- Mechanism to allow cross-origin requests
- Server explicitly permits specific origins

**How It Works:**
```
Browser → OPTIONS request (preflight)
Server → Access-Control-Allow-Origin: https://example.com
Browser → Allowed! Send actual request
```

**Server Response Headers:**
```javascript
// Node.js/Express example
res.setHeader('Access-Control-Allow-Origin', '*'); // Allow all
res.setHeader('Access-Control-Allow-Origin', 'https://example.com'); // Specific
res.setHeader('Access-Control-Allow-Methods', 'GET, POST, PUT');
res.setHeader('Access-Control-Allow-Headers', 'Content-Type, Authorization');
res.setHeader('Access-Control-Allow-Credentials', 'true'); // Allow cookies
```

**Common CORS Errors:**
```
❌ "CORS policy: No 'Access-Control-Allow-Origin' header"
Fix: Add header on server

❌ "CORS policy: Method PUT not allowed"
Fix: Add PUT to Access-Control-Allow-Methods
```

---

### **3. Cookies vs LocalStorage vs SessionStorage**

| Feature | Cookies | LocalStorage | SessionStorage |
|---------|---------|--------------|----------------|
| **Capacity** | 4KB | 5-10MB | 5-10MB |
| **Sent to server** | ✅ Every request | ❌ Client only | ❌ Client only |
| **Expiration** | Set by server | Never (manual clear) | Tab close |
| **Access** | Client & Server | Client only | Client only |
| **Scope** | Domain + Path | Domain | Domain + Tab |
| **Use case** | Auth tokens, tracking | App state, cache | Temp data |

**Cookie Attributes:**
```javascript
document.cookie = "session=abc123; " +
                  "Expires=Wed, 21 Oct 2025 07:28:00 GMT; " +
                  "Secure; " +        // HTTPS only
                  "HttpOnly; " +      // No JS access
                  "SameSite=Strict";  // CSRF protection
```

**When to Use What:**
- **Cookies:** Authentication (HttpOnly, Secure)
- **LocalStorage:** User preferences, cached data
- **SessionStorage:** Multi-step forms, temporary state

---

### **4. Sessions vs Tokens**

**Session-Based Auth:**
```
1. User logs in
2. Server creates session, stores in database
3. Server sends session ID via cookie
4. Browser sends cookie with every request
5. Server validates session ID
```

**Pros:** Server controls sessions (can revoke)  
**Cons:** Not scalable (server stores state)

**Token-Based Auth (JWT):**
```
1. User logs in
2. Server generates JWT (signed token)
3. Client stores token (LocalStorage/Cookie)
4. Client sends token in Authorization header
5. Server validates signature
```

**Pros:** Stateless, scalable, works across domains  
**Cons:** Can't revoke (until expiry), larger size

**JWT Structure:**
```
eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.
eyJzdWIiOiIxMjM0NTY3ODkwIiwibmFtZSI6IkpvaG4gRG9lIiwiaWF0IjoxNTE2MjM5MDIyfQ.
SflKxwRJSMeKKF2QT4fwpMeJf36POk6yJV_adQssw5c

│                                              │                                              │
│          Header (Base64)                     │           Payload (Base64)                   │ Signature
```

---

### **5. CSR vs SSR vs SSG**

**CSR (Client-Side Rendering):**
```
Server → Sends empty HTML + JS bundle
Browser → Downloads JS → Renders page
```
- ✅ Fast navigation after load
- ❌ Slow initial load
- ❌ Bad SEO
- Example: React SPA, Vue SPA

**SSR (Server-Side Rendering):**
```
Server → Generates full HTML → Sends to browser
Browser → Displays immediately → Hydrates with JS
```
- ✅ Fast initial load
- ✅ Good SEO
- ❌ Slower server response
- Example: Next.js, Nuxt.js

**SSG (Static Site Generation):**
```
Build time → Generate all pages as static HTML
Server → Serves pre-built HTML files
```
- ✅ Blazing fast
- ✅ Best SEO
- ❌ Rebuild needed for updates
- Example: Gatsby, Next.js (SSG mode)

---

### **6. REST vs GraphQL vs WebSocket**

**REST API:**
```
GET /api/users/123
GET /api/users/123/posts
GET /api/posts/456/comments
```
- ✅
