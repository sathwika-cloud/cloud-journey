# Networking — DHCP & NAT

## 1. DHCP

**DHCP = Dynamic Host Configuration Protocol**

DHCP automatically provides network configuration to devices when they connect to a network.

It can provide:

* IP address
* Subnet mask / prefix
* Default gateway
* DNS server
* Lease information

### Example

```text
Laptop connects to Wi-Fi
        ↓
DHCP Server (usually router)
        ↓
IP: 192.168.1.20
Gateway: 192.168.1.1
DNS: 192.168.1.1
```

---

## 2. DORA

The DHCP process is commonly remembered as **DORA**:

```text
D → Discover
O → Offer
R → Request
A → Acknowledgment
```

### Discover

Client asks if a DHCP server is available.

### Offer

DHCP server offers an IP address and network configuration.

### Request

Client requests the offered configuration.

### Acknowledgment (ACK)

DHCP server confirms the assignment.

---

## 3. DHCP Lease

DHCP usually does not give an IP permanently.

It gives the device an IP for a specific period called a **lease**.

The device can renew the lease.

---

# NAT

## 4. NAT

**NAT = Network Address Translation**

NAT translates addresses as traffic passes between network boundaries.

A common use is allowing devices with private IP addresses to communicate with the Internet using a public IP.

```text
Laptop
192.168.1.20
     ↓
   Router
     ↓
    NAT
     ↓
 Public IP
     ↓
  Internet
```

---

## 5. Why NAT is Needed

Private IP addresses are not globally routable on the public Internet.

Example home network:

```text
Laptop → 192.168.1.20
Phone  → 192.168.1.21
TV     → 192.168.1.22
```

These devices can share one public IP through NAT.

---

## 6. NAT and Ports

NAT commonly keeps track of connections using IP addresses and port numbers.

Example:

```text
192.168.1.20:51532
        ↓
       NAT
        ↓
Public-IP:62001
```

Another device can have:

```text
192.168.1.21:51533
        ↓
       NAT
        ↓
Public-IP:62002
```

The NAT device maintains these mappings so returning traffic can be sent to the correct internal device.

---

## 7. DHCP vs NAT

```text
DHCP
→ Provides network configuration to a device.

NAT
→ Translates addresses for connections across a network boundary.
```

### Remember

```text
DHCP → "What network configuration should I use?"

NAT → "How should this connection's address be translated?"
```

---

## Key Points

* DHCP = Dynamic Host Configuration Protocol
* DHCP automatically provides network configuration
* Router commonly acts as DHCP server in home networks
* DORA = Discover → Offer → Request → Acknowledgment
* DHCP assignment is usually a lease
* NAT = Network Address Translation
* NAT commonly allows private-IP devices to communicate through a public IP
* NAT uses connection/address/port mappings to track traffic
* DHCP and NAT perform different functions
