<p align="center" style="margin-bottom: 0px !important;">
  <img width="600" src="https://github.com/mithraskuipers/mithraskuipers/blob/master/readme_srcs/42/logo.png?raw=true" alt="42_Network_Amsterdam" align="center"> </p>
<h1 align="center" style="margin-top: 0px;">Net_Practice <a href="https://github.com/JaeSeoKim/badge42"><img src="https://badge42.vercel.app/api/v2/cl483ajsd008309l6suq9l256/project/2861882" alt="mikuiper's 42 NetPractice Score" /></a>

<p align="center" style="margin-top: 0px;">
<img src="https://forthebadge.com/images/badges/made-with-c.svg"/>
<img src="https://forthebadge.com/images/badges/built-with-love.svg"/>
</p>

## :book: About the project

In this project, you will delve into the concept of subnetting, which involves dividing a larger network into smaller subnetworks. This process plays a crucial role in network management by improving performance, enhancing security, and optimizing resource allocation. Understanding subnet formats, including their binary, bits per byte, and decimal representations, is essential for effective network configuration and administration.

By grasping subnet formats, you can efficiently configure IP addresses, determine address ranges, and allocate appropriate resources within each subnetwork. This knowledge enables efficient routing, effective communication, and better control over network traffic. Additionally, understanding subnetting facilitates troubleshooting network connectivity issues and implementing access control policies based on subnets. By gaining proficiency in subnetting, you will acquire valuable skills in network design, optimization, and troubleshooting, empowering you to manage networks with greater efficiency and ensure seamless communication within the network infrastructure.

### Something to get started..
---

Take a moment to explore the table below, which presents various subnet formats used in the NetPractice project, except for the binary representation. This table was designed to aid comprehension of the distinct formats and their structures.

The table provides insights into the bits per byte and decimal representations for each subnet format. By examining the table, you can grasp the relationship between the binary notation, byte notation, and CIDR notation. The inclusion of the binary notation helps establish connections and enhance understanding of how different notations correspond to each other.

By studying this table, you can gain a deeper understanding of subnet formats and how they are represented in different notations. This knowledge will enable you to effectively configure and manage subnets, allocate IP addresses, and optimize network performance.

| CIDR | Bits per Byte (Σ) | Binary                  | Decimal        |
|------|------------------|-------------------------|----------------|
| /32  | 8.8.8.8 (32)     | 11111111.11111111.11111111.11111111 | 255.255.255.255 (255=128+64+32+16+8+4+2+1) |
| /30  | 8.8.8.6 (30)     | 11111111.11111111.11111111.11111100 | 255.255.255.252 (252=128+64+32+16+8+4) |
| /28  | 8.8.8.4 (28)     | 11111111.11111111.11111111.11110000 | 255.255.255.240 (240=128+64+32+16) |
| /27  | 8.8.8.3 (27)     | 11111111.11111111.11111111.11100000 | 255.255.255.224 (224=128+64+32) |
| /26  | 8.8.8.2 (26)     | 11111111.11111111.11111111.11000000 | 255.255.255.192 (192=128+64) |
| /24  | 8.8.8.0 (24)     | 11111111.11111111.11111111.00000000 | 255.255.255.0 (0) |

## Important concepts
---

### TCP: Transport Layer
---
TCP stands for **Transmission Control Protocol**. It is a communication standard that facilitates the exchange of messages between application programs and devices over a network. TCP is responsible for sending packets of data across the internet.

TCP ensures the integrity of data being transmitted over a network. Before transmitting data, TCP establishes a connection between a source and its destination, which remains active until communication begins. It breaks down large amounts of data into smaller packets while ensuring end-to-end delivery without any loss of data.

### IP Address: Network Layer
---
IP (Internet Protocol) is a crucial part of the internet protocol suite, which includes the Transmission Control Protocol (TCP). Together, they are known as TCP/IP. This protocol suite governs rules for packetizing, addressing, transmitting, routing, and receiving data over networks.

IP addressing is a logical method of assigning addresses to devices on a network. Each device connected to the internet requires a unique IP address.

An IP address consists of two parts: one part identifies the host (e.g., a computer or device), and the other part identifies the network to which it belongs. TCP/IP uses a subnet mask to separate these parts.

#### IPv4 vs. IPv6
---
IP addresses come in two versions: IPv4 and IPv6.

IPv4 defines an IP address as a 32-bit number. However, due to the growth of the Internet and the depletion of available IPv4 addresses, a new version called IPv6 was standardized in 1998. IPv6 uses 128 bits for the IP address, but NetPractice only uses IPv4 addresses.

#### Public Address vs. Private Address
---

A public IP address can be accessed directly over the internet and is assigned to your network router by your internet service provider (ISP). It allows your network to connect to the internet from inside to outside.

A private IP address is assigned to a device by the network router. Each device within the same network has a unique private IP address, enabling communication between devices on the internal network.

When a network is connected to the internet, it cannot use an IP address from the reserved private IP address ranges, which are:

- 192.168.0.0 – 192.168.255.255 (65,536 IP addresses)
- 172.16.0.0 – 172.31.255.255 (1,048,576 IP addresses)
- 10.0.0.0 – 10.255.255.255 (16,777,216 IP addresses)

### Subnet Mask
---
A subnet mask is a 32-bit (4-byte) address used to distinguish between a network address and a host address in an IP address. It defines the range of IP addresses that can be used within a network or subnet.

#### Finding the network address
---
Let's take the example of _Interface A1_ with the following properties:

IP address: 104.198.241.125
Mask: 255.255.255.128

To determine the network address, we need to apply the mask to the IP address. Let's convert the mask to its binary form:

Mask: 11111111.11111111.11111111.10000000

In the mask, the bits that are 1 represent the network address, while the bits that are 0 represent the host address. Let's convert the IP address to binary form:

IP address: 01101000.11000110.11110001.01111101
Mask: 11111111.11111111.11111111.10000000

We can now apply a bitwise AND between the IP address and the mask to find the network address:

Network address | 01101000.11000110.11110001.00000000

Which translates to a network address of `104.198.241.0`.

#### Finding the range of host addresses
---
To determine what host addresses we can use on our network, we have to use the bits of our IP address dedicated to the host address. Let's use our previous IP address and mask:

IP address | 01101000.11000110.11110001.01111101
Mask | 11111111.11111111.11111111.10000000

The possible range of our host addresses is expressed through the last 7 bits of the mask which are all 0. Therefore, the range of host addresses is:

| Format  | Start Range | End Range |
|---------|-------------|-----------|
| BINARY  | 00000000    | 01111111  |
| DECIMAL | 0           | 127       |

To get the range of possible IP addresses for our network, we add the range of host addresses to the network address. Our range of possible IP addresses becomes `104.198.241.0 - 104.198.241.127`.

**However**, the extremities of the range are reserved for specific uses and cannot be given to an interface:

104.198.241.0 | Reserved to represent the network address.
104.198.241.127 | Reserved as the broadcast address; used to send packets to all hosts of a network.

Therefore, our real IP range becomes `104.198.241.1 - 104.198.241.126`
#### CIDR Notation (/24)
---
The mask can also be represented with the Classless Inter-Domain Routing (CIDR). This form represents the mask as a slash "/", followed by the number of bits that serve as the network address.

Therefore, the mask in the example above of `255.255.255.128`, is equivalent to a mask of `/25` using the CIDR notation, since 25 bits out of 32 bits represent the network address.

### Switch
---

A switch connects multiple devices together in a single network. Unlike a router, the switch does not have any interfaces since it only distributes packets to its local network, and cannot talk directly to a network outside of its own.

### Router
---
Just as the switch connects multiple devices on a single network, the router connects multiple networks together. The router has an interface for each network it connects to.

Since the router separates different networks, the range of possible IP addresses on one of its interfaces must not overlap with the range of its other interfaces. An overlap in the IP address range would imply that the interfaces are on the same network.

#### Routing Table
---
A routing table is a data table stored in a router or a network host that lists the routes to particular network destinations. In NetPractice, the routing table consists of 2 elements:

- **Destination**: The destination specifies a network address on which a host is the end target of the packets. The route of `default` or `0.0.0.0/0`, is the route that takes effect when no other route is available for an IP destination address. The default route will use the next-hop address to send the packets on their way without giving a specific destination. The default route will match any network.
- **Next hop**: The next hop refers to the next closest router a packet can go through. It is the IP address of the next router on the packet's way. Every single router maintains its routing table with a next hop address.
