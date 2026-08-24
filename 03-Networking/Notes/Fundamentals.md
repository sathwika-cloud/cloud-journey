# Networking - Section 1: Fundamentals

## 1. What is a Network?

A network is a group of devices connected together so they can communicate and exchange data.

Example:

Laptop -> Wi-Fi Router -> Internet -> Server

Data sent over a network is broken into smaller units called packets.

---

## 2. Important Networking Terms

### IP Address

An IP address is a logical address used to identify a device/interface on a network and help route traffic.

Example:

192.168.1.20

Think:
IP = Where is the device?

---

### MAC Address

A MAC address is an address associated with a network interface (NIC) used at the local network/link level.

Example:

A4:5E:60:12:AB:91

Think:
MAC = Which network interface on the local network?

---

### Port

A port identifies a service/application endpoint on a device.

Example:

192.168.1.20:443

192.168.1.20 -> IP address
443 -> Port

Think:
IP = Device/address
Port = Service/application endpoint

---

### Protocol

A protocol is a set of rules that defines how devices communicate.

Examples:

- HTTP -> Web communication
- HTTPS -> Secure web communication
- TCP -> Reliable transport
- UDP -> Connectionless transport
- DNS -> Domain name resolution
- SSH -> Secure remote access

---

## 3. Local Network

A local network is a network where devices are connected within the same nearby network.

Example:

Laptop
   |
Phone ---- Wi-Fi Router
   |
TV

The laptop, phone and TV are part of the same local network.

The router connects this local network to other networks, such as the Internet.

---

## 4. Switch vs Router

### Switch

A switch connects devices within the same local network.

Example:

Laptop ----\
PC -------- Switch
Printer ----/

A switch primarily uses MAC addresses to forward traffic within the local network.

Remember:

Switch -> connects devices locally

---

### Router

A router connects different networks.

Example:

Home Network -> Router -> Internet -> Other Network

A router uses IP addresses and routing information to determine where traffic should go.

Remember:

Router -> connects different networks

---

## 5. Client and Server

### Client

A client is a device or application that requests a service.

Examples:

- Browser
- Phone
- Laptop

### Server

A server is a system that provides a service to clients.

Examples:

- Web server
- Database server
- DNS server
- File server

Basic communication:

Client -> Request -> Server
Client <- Response <- Server

---

# 6. OSI Model

The OSI model is a conceptual model that divides network communication into 7 layers.

| Layer | Name | Important Concepts |
|------:|------|--------------------|
| 7 | Application | HTTP, DNS, SSH |
| 6 | Presentation | Encoding, encryption, compression |
| 5 | Session | Session management |
| 4 | Transport | TCP, UDP |
| 3 | Network | IP, Routing |
| 2 | Data Link | MAC, Ethernet, Wi-Fi |
| 1 | Physical | Signals, cables, radio, fiber |

### Important Layers for Cloud

Layer 7 - Application
-> HTTP, DNS, SSH

Layer 4 - Transport
-> TCP, UDP

Layer 3 - Network
-> IP, Routing

Layer 2 - Data Link
-> MAC, Ethernet, Wi-Fi

Layer 1 - Physical
-> Signals and physical transmission

---

## 7. OSI Data Flow

When accessing a website, networking can be visualized as:

Application
    |
HTTP / HTTPS
    ↓
Transport
    |
TCP / UDP
    ↓
Network
    |
IP / Routing
    ↓
Data Link
    |
MAC / Ethernet / Wi-Fi
    ↓
Physical
    |
Signals / Cable / Radio / Fiber

Important mental model:

Application -> WHAT
Transport -> HOW to transport
Network -> WHERE
Data Link -> LOCAL delivery
Physical -> HOW bits physically travel

---

# 8. TCP/IP Model

The TCP/IP model is another way of organizing networking concepts and is commonly used to describe Internet networking.

| TCP/IP Layer | Examples |
|--------------|----------|
| Application | HTTP, DNS, SSH |
| Transport | TCP, UDP |
| Internet | IP, Routing |
| Network Access | Ethernet, Wi-Fi, MAC |

OSI:
7 layers and mainly a conceptual/reference model.

TCP/IP:
Practical model used to describe Internet networking.

---

# 9. Quick Revision

IP
-> Logical addressing and routing

MAC
-> Network interface / local link

Port
-> Service/application endpoint

Protocol
-> Rules for communication

Switch
-> Connects devices within a local network

Router
-> Connects different networks

OSI:
Application -> HTTP/DNS/SSH
Transport -> TCP/UDP
Network -> IP/Routing
Data Link -> MAC/Ethernet/Wi-Fi
Physical -> Signals
