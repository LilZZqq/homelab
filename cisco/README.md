# 🖧 Cisco Packet Tracer Projects

A collection of network design and simulation projects built using Cisco Packet Tracer, progressing from basic LAN configurations to complex enterprise multi-site topologies.

---

## 01 — Static LAN Configuration
**File:** `01-static-lan-configuration.pkt`

A basic LAN setup with a Cisco 2911 router connected to a 2960 switch with 4 PCs. All devices configured with static IP addresses. Demonstrates fundamental network connectivity and router/switch configuration.

**Concepts covered:**
- Static IP addressing
- Router and switch basic configuration
- Star topology design
- Default gateway configuration

---

## 02 — Network Segmentation (Office & Guest)
**File:** `02-network-segmentation-office-guest.pkt`

Network divided into three segments — Office 1, Guest Office, and Flat 1 — connected through a central switch and customer router to an ISP. Demonstrates basic network segmentation and traffic separation.

**Concepts covered:**
- Network segmentation
- Multiple subnet design
- Customer router to ISP connectivity
- Traffic separation between zones

---

## 03 — Multi-VLAN Network with VoIP
**File:** `03-multi-vlan-voip-network.pkt`

Three-department network (green/blue/red zones) with dedicated VoIP phones in the red zone, a printer in the green zone, laptops in the blue zone, all managed through a central switch connected to a customer router and ISP.

**Concepts covered:**
- VLAN segmentation
- VoIP integration (Cisco 7960 IP Phones)
- Multi-department network design
- Inter-department connectivity

---

## 04 — PC to ISP Connectivity
**File:** `04-pc-to-isp-connectivity.pkt`

End-to-end network simulation showing full connectivity from end-user PCs through a customer router to an ISP router. Demonstrates basic routing and NAT concepts.

**Concepts covered:**
- End-to-end routing
- Customer to ISP connectivity
- NAT concepts
- Basic router configuration

---

## 05 — Two Office WAN with Static DHCP
**File:** `05-two-office-wan-static-dhcp.pkt`

Two geographically separate offices (Office 1 and Office 2) connected via a WAN link between two routers. Each office has its own switch and PCs with static DHCP configuration.

**Concepts covered:**
- WAN connectivity between sites
- Static DHCP configuration
- Inter-office routing
- Multi-router network design

---

## 06 — Enterprise Multi-Site Network
**File:** `06-enterprise-multisite-network.pkt`

The most complex project — a full enterprise topology with 3 buildings each having dedicated switches and routers, an HQ network provider segment, a separate office segment, all connected through an ISP. 35+ devices total.

**Concepts covered:**
- Enterprise multi-site architecture
- Hierarchical network design
- Multiple routers and switches
- HQ and branch connectivity
- ISP integration
- Building-level network segmentation

---

## 🔄 In Progress

- VLAN segmentation with Inter-VLAN routing and ACL firewall rules
- DHCP server per VLAN
- Site-to-site VPN simulation
- OPNsense firewall configuration

---

## Tools Used
- Cisco Packet Tracer 8.x
- Cisco 2811, 2901, 2911 Routers
- Cisco 2960, 3560 Switches
- Cisco 7960 IP Phones
