# Networking — HTTP & HTTPS

## 1. HTTP

**HTTP = Hypertext Transfer Protocol**

HTTP is a protocol used for communication between clients and web servers.

```text
Client
  ↓
HTTP Request
  ↓
Web Server
  ↓
HTTP Response
  ↓
Client
```

---

## 2. Client

A **client** is the application/device that makes a request.

Example:

```text
Browser → Client
```

---

## 3. Server

A **server** receives requests and provides responses/resources.

It can provide:

* Web pages
* APIs
* Files
* Images
* Application data

---

## 4. HTTP Request

Example:

```text
GET / HTTP/1.1
Host: example.com
```

The request tells the server what the client wants.

---

## 5. HTTP Methods

```text
GET
→ Retrieve data

POST
→ Send/create data

PUT
→ Replace/update a resource

PATCH
→ Partially update a resource

DELETE
→ Delete a resource
```

---

## 6. HTTP Response

The server sends a response containing a status code and potentially data/content.

Example:

```text
HTTP/1.1 200 OK
```

```text
Client
  ↓
GET /
  ↓
Server
  ↓
200 OK + Response data
```

---

## 7. HTTP Status Codes

### 2xx — Success

```text
200 → OK
```

### 3xx — Redirection

```text
301 → Moved Permanently
302 → Found / Temporary Redirect
```

### 4xx — Client/request problem

```text
400 → Bad Request
401 → Unauthorized
403 → Forbidden
404 → Not Found
```

### 5xx — Server-side problem

```text
500 → Internal Server Error
502 → Bad Gateway
503 → Service Unavailable
```

Important:

```text
200 → Success
404 → Resource not found
500 → Server-side error
```

---

## 8. HTTP Headers

Headers carry additional information about HTTP requests and responses.

Example:

```text
GET / HTTP/1.1
Host: example.com
User-Agent: Chrome
Accept: text/html
```

Response:

```text
HTTP/1.1 200 OK
Content-Type: text/html
```

---

# HTTPS

## 9. HTTPS

**HTTPS = Hypertext Transfer Protocol Secure**

HTTPS is HTTP communication protected using **TLS (Transport Layer Security)**.

```text
HTTP + TLS
    ↓
  HTTPS
```

HTTPS provides protection such as encryption, authentication, and integrity.

---

## 10. HTTP vs HTTPS

```text
HTTP
→ Port 80
→ No TLS protection

HTTPS
→ Port 443
→ HTTP protected using TLS
```

---

## 11. TLS

**TLS = Transport Layer Security**

TLS provides security features including:

* Encryption
* Authentication
* Integrity protection

Remember:

```text
TLS → provides security for HTTPS
```

---

## 12. HTTPS Certificates

HTTPS uses certificates to help authenticate the server.

Simplified:

```text
Browser
   ↓
"Prove you are example.com"
   ↓
Server
   ↓
Certificate
   ↓
Browser verifies certificate
   ↓
Secure communication
```

Certificates are issued by trusted **Certificate Authorities (CAs)**.

---

# Complete Website Request

## 13. What happens when I type:

```text
https://example.com
```

### Step 1 — DNS

Find the destination IP.

```text
example.com
     ↓
DNS
     ↓
Destination IP
```

### Step 2 — Routing

Determine whether the destination is local or remote.

If remote:

```text
Laptop
   ↓
Default Gateway
   ↓
Router
```

### Step 3 — NAT

On a typical home network, the private source address/port may be translated as traffic passes through the router.

```text
192.168.1.20:51532
        ↓
       NAT
        ↓
Public-IP:62001
```

### Step 4 — TCP

Establish the TCP connection:

```text
SYN
 ↓
SYN-ACK
 ↓
ACK
```

### Step 5 — TLS

Because HTTPS is being used:

```text
TLS
 ↓
Secure communication
```

### Step 6 — HTTP Request

The browser sends an HTTP request:

```text
GET /
Host: example.com
```

### Step 7 — HTTP Response

The server responds:

```text
200 OK
```

along with the requested content.

---

## 14. Complete Mental Model

```text
Domain
  ↓
DNS
  ↓
Destination IP
  ↓
Routing
  ↓
Default Gateway
  ↓
NAT
  ↓
Internet
  ↓
Server:443
  ↓
TCP
  ↓
TLS
  ↓
HTTP Request
  ↓
HTTP Response
```

---

## Key Points

* HTTP = Hypertext Transfer Protocol
* HTTP is used for client-server web communication
* Client = makes the request
* Server = receives requests and provides responses
* GET = retrieve data
* POST = create/send data
* PUT = replace/update
* PATCH = partial update
* DELETE = delete
* `200` = success
* `404` = resource not found
* `500` = server-side error
* HTTP = port 80
* HTTPS = port 443
* HTTPS = HTTP protected using TLS
* TLS = Transport Layer Security
* TLS provides encryption, authentication and integrity protection
* HTTPS certificates help authenticate the server
