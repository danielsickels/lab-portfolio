# Lab Portfolio

A quick-reference guide to two fundamental networking devices—**switches** and **routers**—plus key terms that show up in day-to-day conversations.

---

## Switch (Networking Hub)

A switch connects devices **within** a single computer network.  
It uses **packet switching** to receive data and forward it to the proper destination device.

- **Packets** – short bursts of data forwarded at the **data-link layer** (Layer 2 of the OSI model).  
- Some switches include **Layer-3 (routing) functionality**, letting them make forwarding decisions based on IP addresses as well.  
- Destinations are usually determined by **MAC addresses** stored in the switch’s CAM table.

---

## Router

A router connects **multiple networks** together—think of it as the highway system linking separate cities.

- Reads **IP addresses** and chooses the most efficient path for each packet.
- Lets many devices on the same local network share a single upstream connection (e.g., your home Wi-Fi).  
- Maintains routing tables, applies policies (NAT, ACLs), and can segment traffic for security or performance.

---

## Gateway

Joins two networks that utilize different primary protocols. Serves as an exit and entry point.
- All data should go through a gate before being routed (some examples before leaving are NAT, protocol conversions, security filtering).
-The only data traffic that does not go through a gate might be that among nodes on the same LAN.

---

## Subnet

A "Subnetwork" is a group of devices, or IP addresses, which share a common piece of a main IP address. 
- Offers local traffic to be quick, organized, and easy to be managed by being self contained.
- When data needs sent out if the subnet, it gives it to the router, which forwards the data appropriately.

---

## Subnet Mask

32-bit value to distinguish the host value from the network address within an IP address. It is the last part if the IP address, the 0 in "255.255.255.0".
- Slash (CIDR) form, like /24, is just a shorthand that says “the first 24 bits are network.”

## Key Terms

| Term | Description |
|------|-------------|
| **LAN** (Local Area Network) | A group of interconnected devices confined to a limited geographic area (office, home, campus). |
| **WAN** (Wide Area Network) | Multiple LANs linked over large distances, often via leased lines or public links (the Internet). |
| **Home "Default Gateway"** | Your broadband router takes private 192.168.x.x traffic, translates it (NAT) to a public IP, and puts it on the Internet |
| **VoIP Gateway** | Converts phone calls between traditional land-line signaling and modern IP packets. |
| **API gateway** | Accepts external HTTPS requests, adds security/policy layers, then speaks a different internal micro-service protocol. |
| **Subnet** | A contiguous block of IP addresses that share the same network prefix (defined by a subnet mask / CIDR length); all hosts within that block belong to the same Layer-2 broadcast domain and can reach each other directly without traversing a router. |
| **Subnet Mask** | A subnet mask is a 32-bit pattern marking the network bits of an IPv4 address, letting devices decide if traffic stays local or goes to a router. |

---