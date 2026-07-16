# Logy Tech Company Network Implementation

**Academic Project Repository**
**Institution:** University of Science and Technology, Sana'a
**Author:** Ezz Aldeen Abdulfattah Abdoh Abdulsalam Alshalafi (ID: 202310101160)
**Supervisor:** Dr. Ameen
**Date of Submission:** August 18th, 2025

---

## 1. Project Mandate
This repository contains the comprehensive configuration files and documentation required for the design and implementation of a secure, multi-department enterprise network for Logy Tech Company. The primary objective of this project is to bridge theoretical Cisco Certified Network Associate (CCNA) principles with practical application. Consequently, the network is engineered to resolve complex, real-world routing and switching challenges for a multi-branch corporate entity spanning two distinct geographical locations in Dubai (Downtown and Business Bay).

## 2. Network Topology & Architectural Design
To ensure scalability and fault tolerance, the network architecture is built upon a highly resilient three-tier hierarchical model. This structure is delineated as follows:
*   **Core Layer:** The robust backbone of the network is established by two redundant routers (Core-R1, Core-R2) working in conjunction with two multilayer switches (MLSW-1, MLSW-2) to facilitate high-speed packet routing and gateway redundancy.
*   **Distribution Layer:** Dedicated multilayer switches are deployed per floor in each location. These devices effectively aggregate departmental traffic and enforce inter-VLAN routing policies.
*   **Access Layer:** Serving as the network's edge, this layer connects departmental end-user devices and Cisco Aironet Access Points (APs) to the enterprise infrastructure via secure access ports.

## 3. Implemented Technologies & Protocols
The system configuration rigorously adheres to CCNA standards, integrating a suite of advanced protocols to optimize security, connectivity, and performance. The key implementations include:
*   **VLAN Segmentation & Routing:** To maintain departmental isolation and minimize broadcast domains, distinct VLANs (e.g., Sales VLAN 10, HR VLAN 20) were configured. Inter-VLAN communication is systematically managed through Switch Virtual Interfaces (SVIs) on the Layer-3 Multilayer Switches.
*   **Dynamic IP Allocation:** IP addressing is dynamically provisioned by a centralized DHCP Server located in the secure Server Room (VLAN 60). To support this, distribution switches utilize IP helper-addresses to securely relay DHCP requests across broadcast boundaries.
*   **Routing Protocols:** Network reachability across the diverse branches is achieved via OSPF dynamic routing. Furthermore, default and static routes are explicitly defined to direct external traffic toward the ISP gateways.
*   **Comprehensive Security Policies:** 
    *   *Access Control Lists (ACLs):* Extended ACLs are strictly enforced to prevent unauthorized inter-departmental data access, such as isolating the Marketing department from Finance resources.
    *   *Port Security:* Edge ports are secured using MAC address sticky learning coupled with immediate violation shutdown protocols to mitigate rogue device connections.
    *   *Remote Access:* Administrative management is exclusively facilitated through secure, encrypted SSH sessions (RSA 1024).
*   **Network Address Translation (NAT):** Port Address Translation (PAT/NAT Overload) is configured at the edge to enable secure, multiplexed internet access for the internal corporate network.
*   **Quality of Service (QoS):** To mitigate latency during periods of high network congestion, strict priority queuing mechanisms are established for delay-sensitive voice and video traffic.
*   **Management & Logging:** Centralized network visibility is maintained through Simple Network Management Protocol (SNMP) configurations and timestamped syslog forwarding, which are essential for systematic auditing and troubleshooting.

## 4. Repository Structure
The repository is organized logically to facilitate review and deployment:
*   `/configs/`: Contains the raw Command Line Interface (CLI) configuration scripts tailored for the Core Routers, Multilayer Switches, Access Switches, and ISP gateways.
*   `/docs/`: Houses the comprehensive project design report and detailed IP addressing scheme tables.
