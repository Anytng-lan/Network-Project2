# 🌐 Luxor Solutions Network Design

A comprehensive network architecture designed for **Luxor Solutions**, a mid-sized enterprise with a 5-floor office building. The design focuses on scalability, efficiency, and fault tolerance while implementing static routing, VLSM, and hybrid topologies.

---

## 🧠 Project Overview

- **Company**: Luxor Solutions  
- **Location**: 5-floor office building  
- **Objective**: Structured network for internal communication, server access, and scalability  
- **Tools Used**: Cisco Packet Tracer, IP Subnetting (VLSM), Static Routing

---

## 📊 Network Statistics

| Metric                    | Value                                    |
|---------------------------|------------------------------------------|
| **Total Floors**          | 5                                        |
| **Total Hosts**           | 12,573                                   |
| **Total Subnetworks**     | 8 (5 Floor LANs + 3 Inter-Router Links)  |
| **Total Routers**         | 5 (3 Edge + 2 Intermediate/Core)         |
| **Total Switches**        | 5 (1 per floor)                          |
| **Routing Type**          | Static Routing                           |
| **Default Gateways**      | 5 (1 per floor)                          |
| **Total Servers**         | 5 (DNS, DHCP, Email, HTTP, FTP)          |
| **IP Classes Used**       | Class B (Floors 1–3), Class A (Floors 4–5), Class C (/30 P2P Links) |
| **Topologies Used**       | Bus (Floors 1–3), Star (Floors 4–5)      |
| **IP Addressing Scheme**  | VLSM (Classless, Efficient Allocation)   |
| **Backbone Links**        | /30 Subnets for minimal IP waste         |
| **Broadcast Domains**     | 5 (one per floor)                        |

---

## 🧩 Network Architecture

- **Floors 1, 2, 3**: Bus Topology (Cost-efficient, fewer cables)
- **Floors 4, 5**: Star Topology (High reliability and easier troubleshooting)
- **Central Core Router** connects all floor routers via /30 backbone links

---

## 🛠️ Server Placement

| Server      | Location  |
|-------------|-----------|
| DNS         | Floor 1   |
| Email       | Floor 2   |
| DHCP        | Floor 3   |
| HTTP & FTP  | Floor 5   |

---

## 📦 IP Addressing Scheme (VLSM)

| Floor | Hosts | Network         | CIDR | Subnet Mask     | Gateway        | IP Class |
|-------|-------|------------------|------|------------------|----------------|----------|
| 1     | 283   | 172.16.0.0       | /23  | 255.255.254.0    | 172.16.0.1     | B        |
| 2     | 9313  | 172.16.64.0      | /18  | 255.255.192.0    | 172.16.64.1    | B        |
| 3     | 2347  | 172.16.128.0     | /20  | 255.255.240.0    | 172.16.128.1   | B        |
| 4     | 409   | 10.0.0.0         | /23  | 255.255.254.0    | 10.0.0.1       | A        |
| 5     | 221   | 10.0.2.0         | /24  | 255.255.255.0    | 10.0.2.1       | A        |
| Links| 2 per  | 192.168.0.0/30 → /30 | 255.255.255.252 | e.g., 192.168.0.1–10 | C        |

---

## 🚦 Routing Strategy

- **Static Routing** via centralized Core Router
- Routers manually configured with:
  - Routes to all other subnets
  - Minimal routing table size
  - Deterministic, low-latency paths

---

## ✅ Best Practices Applied

- 🔧 VLSM for optimal address utilization  
- 🔐 Subnet isolation for security  
- 📈 Hierarchical design for scalability  
- 🌍 Strategic server distribution to reduce inter-floor traffic  
- 🚧 Static routing to minimize complexity and increase performance  

---

## 📁 Repository Structure

