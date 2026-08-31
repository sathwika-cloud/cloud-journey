# Networking — Routing

## 1. Routing

**Routing** is the process of deciding where network traffic should go to reach its destination.

```text
Source
  ↓
Routing decision
  ↓
Next hop
  ↓
Destination
```

---

## 2. Local vs Remote Network

Example:

```text
Laptop IP: 192.168.1.20/24
Network:   192.168.1.0/24
```

### Local destination

```text
192.168.1.50
```

This belongs to `192.168.1.0/24`.

→ Send through the local network.

### Remote destination

```text
192.168.2.50
```

This belongs to another network.

→ Send traffic to the default gateway.

---

## 3. Router

A **router connects different networks** and forwards packets between them.

```text
Network A
192.168.1.0/24
      ↓
    Router
      ↓
Network B
192.168.2.0/24
```

---

## 4. Routing Table

A **routing table** contains routes that tell a device where traffic should be forwarded.

Example:

```text
Destination          Next Hop
--------------------------------
192.168.1.0/24       Local
192.168.2.0/24       Router B
0.0.0.0/0            Default Gateway
```

Think of it as a map:

```text
Destination → Where should I send the packet?
```

---

## 5. Next Hop

The **next hop** is the next router/device to which a packet is forwarded.

```text
Laptop
   ↓
Router A
   ↓
Router B
   ↓
Destination
```

Here, Router B is the next hop from Router A.

---

## 6. Default Gateway

The **default gateway** is where a host sends traffic when there is no more specific route for the destination.

Example:

```text
Laptop:
192.168.1.20

Default Gateway:
192.168.1.1
```

If destination is:

```text
192.168.1.50
```

→ Local network.

If destination is:

```text
8.8.8.8
```

→ Send toward `192.168.1.1`.

---

## 7. Default Route

```text
0.0.0.0/0
```

is the common default IPv4 route.

It means:

> Any IPv4 destination that does not match a more specific route.

Example:

```text
Destination          Next Hop
--------------------------------
192.168.1.0/24       Local
0.0.0.0/0            192.168.1.1
```

```text
192.168.1.0/24
→ Local traffic

0.0.0.0/0
→ Everything else
```

---

## 8. Longest Prefix Match

If multiple routes match a destination, the **most specific route** is selected.

Example:

```text
10.0.0.0/8
10.10.0.0/16
10.10.20.0/24
0.0.0.0/0
```

Destination:

```text
10.10.20.50
```

The selected route is:

```text
10.10.20.0/24
```

because `/24` is more specific than `/16` and `/8`.

This is called **Longest Prefix Match**.

### Rule

> Most specific matching route wins.

---

## 9. Routing vs NAT

### Routing

Determines:

> Where should the packet go?

### NAT

Translates:

> The address information used by the connection.

```text
Routing → chooses the path

NAT → translates addresses
```

They can happen on the same router but are different functions.

---

## 10. Internet Gateway

In AWS, an **Internet Gateway (IGW)** provides a path between a VPC and the Internet.

Example:

```text
AWS VPC
   ↓
Internet Gateway
   ↓
Internet
```

A route can be:

```text
0.0.0.0/0 → Internet Gateway
```

Meaning:

> Send traffic for destinations outside the VPC toward the Internet Gateway.

---

## 11. Internet Gateway vs NAT Gateway

```text
Internet Gateway
→ Provides a VPC's path to/from the Internet.

NAT Gateway
→ Allows private-subnet resources to initiate
  Internet connections without giving them
  public IPv4 addresses.
```

They are different AWS components.

---

## Example

Laptop:

```text
192.168.1.20/24
```

Destination:

```text
8.8.8.8
```

Process:

```text
8.8.8.8
   ↓
Not in local network
   ↓
Default route
   ↓
Default Gateway
   ↓
Router
   ↓
Other networks
   ↓
Internet
```

---

## Key Points

* Routing = deciding where traffic should go
* Router = connects different networks
* Routing table = contains routes to destinations
* Next hop = next device/router to forward traffic to
* Default gateway = used when no more specific route exists
* `0.0.0.0/0` = default IPv4 route
* Longest Prefix Match = most specific matching route wins
* Internet Gateway = AWS VPC's path to/from the Internet
* Routing and NAT are different functions
