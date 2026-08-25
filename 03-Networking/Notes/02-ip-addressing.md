# Networking - Section 2: IP Addressing

## 1. What is an IPv4 Address?

An IPv4 address is a logical address used to identify a network interface on a network and help route traffic.

Example:

192.168.1.20

IPv4 uses 32 bits divided into 4 octets.

192 . 168 . 1 . 20
 8     8    8    8  = 32 bits

Each octet can have a value from 0 to 255.

Example:

0.0.0.0
192.168.1.20
255.255.255.255

---

## 2. Why Do We Need IP Addresses?

Devices on a network need addresses so that data knows where it needs to go.

Example:

Laptop -> 192.168.1.20
Phone  -> 192.168.1.21
TV     -> 192.168.1.22

The IP address helps identify the destination for network traffic.

---

# 3. Network Part and Host Part

An IP address has two conceptual parts:

NETWORK PART | HOST PART

The network part identifies which network the device belongs to.

The host part identifies the particular device/interface within that network.

Example:

192.168.1.20/24

With /24:

192.168.1 | 20
 NETWORK  | HOST

Network:
192.168.1.0/24

Host:
20

Another device could be:

192.168.1.21

Both devices belong to:

192.168.1.0/24

because they have the same network portion.

---

## 4. Why Do We Need Network and Host Parts?

A device needs to determine whether a destination is:

1. On the same local network
2. On a different network

Example:

Laptop:
192.168.1.20/24

Destination:
192.168.1.50

Both are in:

192.168.1.0/24

Therefore, the destination is on the same local network.

But:

Destination:
8.8.8.8

is not part of:

192.168.1.0/24

So the laptop sends the traffic to its default gateway.

---

# 5. Subnet Mask

A subnet mask tells us which portion of an IP address represents the network and which portion represents the host.

Example:

IP:
192.168.1.20

Subnet mask:
255.255.255.0

This corresponds to:

192.168.1.20/24

The /24 means:

24 bits -> Network
8 bits  -> Host

Because IPv4 has 32 bits:

32 - 24 = 8 host bits

---

# 6. CIDR Notation

CIDR stands for Classless Inter-Domain Routing.

CIDR provides a shorter way to represent an IP address and its network prefix.

Example:

192.168.1.20/24

The /24 means:

The first 24 bits are the network portion.

The remaining 8 bits are available for hosts.

IPv4 = 32 bits

Therefore:

32 - 24 = 8 host bits

---

## Common CIDR Examples

### /8

8 network bits
24 host bits

2^24 = 16,777,216 total addresses

---

### /16

16 network bits
16 host bits

2^16 = 65,536 total addresses

---

### /24

24 network bits
8 host bits

2^8 = 256 total addresses

---

### /32

32 network bits
0 host bits

2^0 = 1 address

---

## Important CIDR Rule

The larger the CIDR number, the smaller the network.

Example:

/16 -> larger network
/24 -> smaller network
/28 -> even smaller network
/32 -> one address

Why?

IPv4 always has 32 bits.

When the CIDR number increases:

Network bits increase
        ↓
Host bits decrease
        ↓
Fewer addresses are available
        ↓
Smaller network

Example:

/16:
16 network bits + 16 host bits

/24:
24 network bits + 8 host bits

Therefore /16 is larger than /24.

---

# 7. Subnetting

Subnetting means dividing a larger network into smaller networks called subnets.

Example:

A large network:

10.0.0.0/16

Can be divided into smaller networks such as:

10.0.1.0/24
10.0.2.0/24
10.0.3.0/24
10.0.4.0/24

Each of these is a separate subnet.

### Why use subnets?

Subnets help:

- Organize networks
- Separate different groups of resources
- Control network traffic
- Improve security/isolation
- Design cloud networks

Example in AWS:

VPC
 |
 +--- Public Subnet
 |
 +--- Private Subnet

We will learn AWS VPC and subnets in detail later.

---

# 8. Public vs Private IP Addresses

## Private IP

Private IP addresses are used inside private networks.

The main private IPv4 ranges are:

10.0.0.0/8

172.16.0.0/12

192.168.0.0/16

Examples:

10.0.0.5
172.16.5.10
192.168.1.20

Private IP addresses are not directly routable over the public Internet.

They are commonly used inside:

- Home networks
- Office networks
- Cloud private networks

---

## Public IP

A public IP address is used for communication over the public Internet.

For example:

Home network:

Laptop:
192.168.1.20 (Private IP)

Router:
Public IP assigned by ISP

Conceptually:

Laptop
192.168.1.20
     |
     v
Router
     |
Public IP
     |
     v
Internet

NAT allows devices using private IPs to communicate with the Internet.

NAT will be covered later.

---

# 9. Static vs Dynamic IP

## Static IP

A static/fixed IP remains assigned to a device or interface unless it is deliberately changed.

Example:

Database Server:
10.0.1.50

Applications can consistently connect to the database using its predictable address.

Static/fixed addressing is useful when a resource needs a predictable address.

Examples:

- Servers
- Network infrastructure
- Certain cloud resources

---

## Dynamic IP

A dynamic IP is assigned automatically, commonly using DHCP.

Example:

Laptop connects to Wi-Fi.

Laptop:
"Can I get an IP address?"

DHCP server:
"Here is 192.168.1.20."

The device may receive a different address later depending on the network and DHCP lease.

Dynamic addressing is commonly used for:

- Laptops
- Phones
- TVs
- Other ordinary client devices

### Easy way to remember:

Static -> Fixed/predictable

Dynamic -> Automatically assigned

---

# 10. MAC Address vs IP Address

A network interface already has a MAC address associated with it.

Example:

MAC:
A4:5E:60:12:AB:91

When the device connects to a network, it can be assigned an IP address.

Example:

IP:
192.168.1.20

So:

MAC -> Associated with the network interface

IP -> Address used for communication on a particular network

---

## Example

At home:

MAC:
A4:5E:60:12:AB:91

IP:
192.168.1.20

At college:

The MAC can remain the same, but the IP can change:

MAC:
A4:5E:60:12:AB:91

IP:
10.20.5.47

The IP changes because the laptop is now connected to a different network.

---

# 11. Can a Device Have a MAC Without an IP?

Yes.

The network interface can have a MAC address even when the device is not connected to a network.

Example:

MAC:
A4:5E:60:12:AB:91

IP:
No network-assigned IP

After connecting to Wi-Fi:

MAC:
A4:5E:60:12:AB:91

IP:
192.168.1.20

Usually DHCP is responsible for automatically assigning the IP configuration.

---

# 12. IP Address Does Not Mean Internet Access

A device can have a private IP address without having Internet access.

Example:

Laptop:
192.168.1.20

Router:
192.168.1.1

Even if the Internet connection is down, the laptop can still have its local IP address.

Therefore:

IP address != Internet access

---

# 13. Default Gateway

The default gateway is the device a host sends traffic to when the destination is outside its local network.

Usually, the router acts as the default gateway.

Example:

Laptop:
192.168.1.20/24

Router:
192.168.1.1

Internet:
8.8.8.8

The laptop checks:

Is 8.8.8.8 on my local network?

No.

So:

Laptop
192.168.1.20
      |
      v
Default Gateway
192.168.1.1
      |
      v
Internet

### Remember:

Default Gateway = Where traffic goes when the destination is outside the local network.

---

# 14. Complete Example

Consider:

Laptop:

IP:
192.168.10.25/24

Default Gateway:
192.168.10.1

### What does /24 mean?

24 bits -> Network
8 bits -> Host

### What is the network?

192.168.10.0/24

### What is the host?

25

### Is 192.168.10.30 on the same local network?

Yes.

Both belong to:

192.168.10.0/24

### Is 8.8.8.8 on the same local network?

No.

Therefore, the laptop sends the traffic to:

192.168.10.1

which is the default gateway.

---

# 15. Important Formulas

IPv4:

32 total bits

Host bits:

32 - CIDR prefix

Total addresses:

2^(host bits)

Example:

/24

Host bits:
32 - 24 = 8

Total addresses:
2^8 = 256

In a traditional IPv4 subnet, 2 addresses are reserved for the network and broadcast addresses, so:

Usable hosts = 256 - 2 = 254

Note:
Cloud platforms can have their own subnet-specific address reservations, so don't assume every cloud subnet gives exactly the traditional number of usable addresses.

---

# 16. Quick Revision

IP Address
-> Logical address used for network communication and routing

MAC Address
-> Address associated with a network interface at the local/link level

Network Part
-> Identifies which network the device belongs to

Host Part
-> Identifies the device/interface within that network

Subnet Mask
-> Determines network and host portions

CIDR
-> Represents the network prefix length

Subnetting
-> Dividing a larger network into smaller networks

Private IP
-> Used inside private networks

Public IP
-> Used for communication over the public Internet

Static IP
-> Fixed/predictable address

Dynamic IP
-> Automatically assigned address

DHCP
-> Commonly assigns IP configuration automatically

Default Gateway
-> Device used to reach destinations outside the local network

---

# 17. Section 2 Checklist

- [x] IPv4 address
- [x] IPv4 32-bit structure
- [x] Network part
- [x] Host part
- [x] Subnet mask
- [x] CIDR notation
- [x] CIDR and network size
- [x] Subnetting basics
- [x] Public IP
- [x] Private IP
- [x] Static IP
- [x] Dynamic IP
- [x] DHCP basics
- [x] MAC vs IP
- [x] Default gateway
- [x] Local network concept
