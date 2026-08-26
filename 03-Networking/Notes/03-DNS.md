Section 4 Checklist

- [x] What is DNS?
- [x] What is a domain name?
- [x] Why DNS is needed
- [x] DNS resolution
- [x] DNS resolver
- [x] A record
- [x] AAAA record
- [x] CNAME record
- [x] MX record
- [x] DNS caching
- [x] TTL
- [x] DNS port 53
- [x] DNS and TCP/UDP
- [x] DNS vs Internet
- [x] Complete DNS request flow

# Networking - Section 4: DNS

## 1. What is DNS?

DNS stands for:

Domain Name System

DNS is a system that translates human-readable domain names into information that computers use to communicate over a network.

The most common example is:

google.com
    ↓
DNS
    ↓
IP address

For example:

google.com → an IPv4 address

Humans prefer names such as:

google.com
github.com
amazon.com

Computers ultimately need IP addresses to communicate with network destinations.

Therefore, DNS acts as a directory between names and network information.

---

# 2. What is a Domain Name?

A domain name is a human-readable name used to identify a website or Internet service.

Examples:

google.com
github.com
amazon.com

Instead of remembering an IP address such as:

142.x.x.x

we can use:

google.com

The DNS system can then resolve the domain name to the required network information.

---

# 3. Why Do We Need DNS?

Without DNS, users would have to remember IP addresses.

For example:

Instead of:

https://example.com

we might have to remember:

https://93.184.216.34

This becomes difficult because:

- IP addresses are difficult to remember
- IP addresses can change
- One domain can be associated with multiple IP addresses
- DNS can store different types of information about a domain

Therefore:

DNS provides a convenient naming system for Internet services.

---

# 4. Basic DNS Resolution

When a user enters:

www.example.com

the computer needs to find the IP address associated with it.

Simplified flow:

Browser
   ↓
DNS Resolver
   ↓
DNS system
   ↓
IP address
   ↓
Browser connects to the server

Example:

www.example.com
       ↓
DNS
       ↓
93.184.216.34
       ↓
93.184.216.34:443
       ↓
Web server

---

# 5. What is a DNS Resolver?

A DNS resolver is a service that receives DNS queries and finds the answer.

The computer can ask:

"What is the IP address of example.com?"

The resolver finds the required DNS information and returns the result.

The DNS resolver may be provided by:

- ISP
- Router
- Organization
- Public DNS provider
- Cloud provider

Examples of public DNS resolvers:

Google DNS:
8.8.8.8

Cloudflare DNS:
1.1.1.1

These are examples only; we do not need to memorize them.

---

# 6. DNS Records

DNS does not only store domain → IP mappings.

It has different types of records.

Important records:

A
AAAA
CNAME
MX

---

# 7. A Record

An A record maps a domain/hostname to an IPv4 address.

Example:

example.com
    ↓
A
    ↓
93.184.216.34

Meaning:

"When someone asks for the IPv4 address of example.com, return 93.184.216.34."

Remember:

A → IPv4

---

# 8. AAAA Record

An AAAA record maps a domain/hostname to an IPv6 address.

Example:

example.com
    ↓
AAAA
    ↓
IPv6 address

Remember:

A → IPv4

AAAA → IPv6

We do not need to go deep into IPv6 yet.

---

# 9. CNAME Record

CNAME stands for:

Canonical Name

A CNAME creates an alias from one hostname to another hostname.

Example:

www.example.com
       ↓
     CNAME
       ↓
example.com

This means:

"www.example.com is an alias for example.com."

The important point:

CNAME points to another hostname/domain name.

It does NOT directly contain an IP address.

---

## Why is CNAME useful?

CNAME is useful when multiple names should point to the same destination.

Example:

example.com
www.example.com
shop.example.com

Suppose the main service is:

app.example.com

We can conceptually have:

www.example.com
       ↓
     CNAME
       ↓
app.example.com

shop.example.com
       ↓
     CNAME
       ↓
app.example.com

If the IP address of app.example.com changes, we only need to update the A record for app.example.com.

The CNAME records can remain unchanged.

---

# 10. CNAME Mental Model

Think of CNAME as:

"Another name for this service."

Example:

www.example.com
       ↓
       alias
       ↓
example.com

CNAME does not mean:

"Here is the IP."

Instead it means:

"Look at this other hostname."

Then DNS can continue resolving that hostname.

Example:

www.example.com
       ↓
CNAME
       ↓
example.com
       ↓
A record
       ↓
93.184.216.34

---

# 11. MX Record

MX stands for:

Mail Exchange

An MX record tells the Internet which mail server handles email for a domain.

Example:

Domain:

example.com

Email:

user@example.com

The sending mail system needs to know:

"Which mail server should receive email for example.com?"

It checks the MX record:

example.com
     ↓
    MX
     ↓
mail.example.com

Then:

mail.example.com
       ↓
DNS
       ↓
IP address
       ↓
Mail server

Remember:

MX → Mail server

---

# 12. Common DNS Records

| Record | Purpose |
|--------|---------|
| A | Maps hostname to IPv4 |
| AAAA | Maps hostname to IPv6 |
| CNAME | Alias to another hostname |
| MX | Specifies mail server |

Later we may encounter:

TXT
NS
SOA

These are important in real-world DNS but are not required yet.

---

# 13. DNS Caching

DNS lookups do not always need to happen from scratch.

DNS information can be cached temporarily.

Example:

First request:

Laptop
   ↓
DNS Resolver
   ↓
IP address

The resolver can cache the result.

Later:

Laptop
   ↓
DNS cache
   ↓
IP address

Caching makes DNS lookups faster and reduces unnecessary DNS queries.

---

# 14. TTL

TTL stands for:

Time To Live

TTL specifies how long DNS information can be cached.

Example:

If a DNS record has:

TTL = 3600 seconds

the record can generally be cached for:

3600 seconds = 1 hour

After the cache expires, the DNS information can be queried again.

---

# 15. DNS and Ports

DNS commonly uses:

Port 53

DNS can use:

UDP port 53

and can also use:

TCP port 53

For basic understanding:

DNS → Port 53
Usually UDP

Do not remember:

"DNS only uses UDP."

That is incorrect.

---

# 16. DNS vs Internet

DNS does not carry the actual website content.

DNS answers questions such as:

"What IP address should I connect to?"

Example:

Browser:
"What is the IP for example.com?"

DNS:
"Here is the IP."

Browser:
"Okay, I'll connect to it."

Then the browser communicates with the actual server.

Therefore:

DNS helps FIND the destination.

It does not deliver the webpage itself.

---

# 17. Complete Website Request

Suppose the user enters:

https://example.com

Simplified process:

1. User enters the domain.
2. Browser needs the server's IP.
3. DNS resolution occurs.
4. DNS returns an IP address.
5. Browser connects to that IP.
6. HTTPS communication takes place.
7. The web server responds.

Conceptually:

Domain
   ↓
DNS
   ↓
IP address
   ↓
TCP connection
   ↓
Port 443
   ↓
HTTPS
   ↓
Web server
   ↓
Response

---

# 18. Connecting DNS With Previous Concepts

We previously learned:

IP → identifies the network destination

Port → identifies the service

TCP/UDP → transport protocol

Now we add:

DNS → helps find the IP associated with a name

Therefore:

Domain
   ↓
DNS
   ↓
IP
   ↓
Port
   ↓
TCP/UDP
   ↓
Service

Example:

google.com
    ↓
DNS
    ↓
IP address
    ↓
TCP
    ↓
Port 443
    ↓
HTTPS
    ↓
Web server

---

# 19. Important Points to Remember

DNS
→ Domain Name System

Domain
→ Human-readable name used to identify an Internet service/domain

DNS Resolver
→ Finds answers to DNS queries

A
→ IPv4 address

AAAA
→ IPv6 address

CNAME
→ Alias to another hostname

MX
→ Mail server for a domain

DNS port
→ 53

DNS caching
→ Temporarily stores DNS results

TTL
→ Determines how long DNS information can be cached
---
