# Lab Portfolio

A quick-reference guide to two fundamental networking devices—**switches** and **routers**—plus key terms that show up in day-to-day conversations.

---

## 🌐 Switch (Networking Hub)

A switch connects devices **within** a single computer network.  
It uses **packet switching** to receive data and forward it to the proper destination device.

- **Packets** – short bursts of data forwarded at the **data-link layer** (Layer 2 of the OSI model).  
- Some switches include **Layer-3 (routing) functionality**, letting them make forwarding decisions based on IP addresses as well.  
- Destinations are usually determined by **MAC addresses** stored in the switch’s CAM table.

---

## 🚏 Router

A router connects **multiple networks** together—think of it as the highway system linking separate cities.

- Reads **IP addresses** and chooses the most efficient path for each packet.
- Lets many devices on the same local network share a single upstream connection (e.g., your home Wi-Fi).  
- Maintains routing tables, applies policies (NAT, ACLs), and can segment traffic for security or performance.

### Key Terms

| Term | Description |
|------|-------------|
| **LAN** (Local Area Network) | A group of interconnected devices confined to a limited geographic area (office, home, campus). |
| **WAN** (Wide Area Network) | Multiple LANs linked over large distances, often via leased lines or public links (the Internet). |

---

> **Tip:** When planning a network, remember the simple rule of thumb:  
> *Switches build **networks***, while *routers **connect** them.*

Happy labbing!