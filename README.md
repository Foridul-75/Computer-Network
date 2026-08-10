# 🏥 Design and Implementation of a Smart Multi-Speciality Hospital Network Using Cisco Packet Tracer

## 📌 Project Overview

The **Smart Multi-Speciality Hospital Network** is a Cisco Packet Tracer-based network design and implementation project developed for the **CSE322: Computer Networks Lab** course in the Department of Computer Science and Engineering at **Daffodil International University**.

The project provides a structured, scalable, and efficient network infrastructure for a multi-speciality hospital environment, connecting **six major hospital sites**, each containing multiple departments with dedicated network segments.

The network follows a hierarchical architecture consisting of **ISP Router, ISP Switch, Edge Routers, Core Routers, Access Switches, VLANs, and End Devices**.

- **VLSM** (Variable Length Subnet Masking) is used for efficient IP address allocation based on departmental host requirements.
- **VLANs** separate departments, with **802.1Q trunking** and **Router-on-a-Stick** enabling inter-VLAN communication.
- **DHCP** automatically assigns IP addresses to end devices.
- **EIGRP (AS 100)** provides dynamic routing between internal hospital networks.
- **NAT/PAT** on the Edge Routers provides Internet access to private internal networks.
- **Network services** — HTTP, FTP, DNS, and Email — are configured and tested.
- The complete network is verified using connectivity, routing, DHCP, NAT, and service tests.

---
## 🏥 Network Architecture
<img width="1011" height="525" alt="image" src="https://github.com/user-attachments/assets/9c8533be-9cde-478f-8729-7e747a3f2147" />


## ⚙️ Technologies & Features

- Cisco Packet Tracer
- VLSM-based IP Addressing
- VLAN
- 802.1Q Trunking
- Router-on-a-Stick
- Inter-VLAN Routing
- DHCP
- EIGRP – AS 100
- NAT/PAT
- ISP Connectivity & Internet Access
- HTTP Server
- FTP Server
- DNS Server
- Email Server
- Network Connectivity Testing


## 🌐 IP Addressing

Private IP addressing is used for all internal hospital networks.

### Main Hospital — Network Block: `10.0.0.0/22`

| VLAN | Department | Network | Prefix | Gateway |
|------|-----------|---------|--------|---------|
| 10 | DMZ | 10.0.1.160 | /28 | 10.0.1.161 |
| 20 | Doctors & ICU | 10.0.1.64 | /26 | 10.0.1.65 |
| 30 | Billing & Admin | 10.0.1.0 | /26 | 10.0.1.1 |
| 50 | Guest Wi-Fi | 10.0.0.0 | /24 | 10.0.0.1 |

### Branch Networks

| Site | Network Block |
|------|---------------|
| Diagnostic Center | 10.1.0.0/24 |
| Emergency Clinic | 10.2.0.0/24 |
| Telemedicine Branch | 10.3.0.0/24 |
| Maternity Hospital | 10.4.0.0/24 |
| Children Care Hospital | 10.5.0.0/24 |

> Point-to-point router links use `/30` subnets.


## 🔐 Network Segmentation Using VLAN
Each hospital department is logically separated using VLANs (Main Hospital example):
- VLAN 10 → DMZ
- VLAN 20 → DOCTORS_ICU
- VLAN 30 → BILLING_ADMIN
- VLAN 50 → GUEST_WIFI
  
**Benefits:** department-wise segmentation, reduced broadcast traffic, better network management, improved organization, and logical separation between departments.

## 🚦 Routing — EIGRP
**EIGRP (Enhanced Interior Gateway Routing Protocol)**, Autonomous System **100**, is used for dynamic routing within the hospital network, allowing routers to dynamically learn and exchange routes between hospital sites.


## 🌍 NAT/PAT

NAT/PAT is configured on the Edge Routers to allow private internal networks to access the Internet.
Private IP → Core Router → Edge Router → NAT/PAT → Public Network → ISP → Internet
> Internal `10.0.0.0/8` traffic is treated separately so inter-branch private communication can occur without unnecessary NAT.



## 📡 DHCP

DHCP automatically provides network configuration to end devices, including IP Address, Subnet Mask, Default Gateway, and DNS Server.

**Example — VLAN 20:**
- Network: `10.0.1.64/26`
- Gateway: `10.0.1.65`


## 🖥️ Network Services (DMZ)

- HTTP / Web Server
- FTP Server
- DNS Server
- Email Server
These services are tested from appropriate end devices within the network.

## 🧪 Network Testing & Verification

| Purpose | Command |
|---------|---------|
| Interface Verification | `show ip interface brief` |
| VLAN Verification | `show vlan brief` |
| Trunk Verification | `show interfaces trunk` |
| Routing Verification | `show ip route` |
| EIGRP Verification | `show ip eigrp neighbors` |
| DHCP Verification | `show ip dhcp binding` |
| NAT Verification | `show ip nat translations` |
| Connectivity Testing | `ping` |

HTTP, FTP, DNS, and other configured services are also tested to verify end-to-end network functionality.

---

## 🎯 Project Objectives

1. Design a realistic multi-site hospital network.
2. Efficiently allocate IP addresses using VLSM.
3. Separate hospital departments using VLANs.
4. Implement inter-VLAN communication.
5. Configure automatic IP assignment using DHCP.
6. Implement dynamic routing using EIGRP.
7. Provide Internet access using NAT/PAT.
8. Configure essential network services.
9. Test and verify end-to-end network connectivity.
10. Create a scalable and manageable hospital network infrastructure.

---

## 📂 Repository Contents

| File | Description |
|------|-------------|
| `Computer Network Project .pkt` | Complete Cisco Packet Tracer project |
| `Smart_Hospital_Network_Report_VLSM.pdf` | VLSM and IP addressing configuration |
| `Hospital_VLAN_Config_Report (Final).pdf` | VLAN configuration |
| `Hospital_Edge_Core_IP_Configuration.pdf` | Edge and Core Router IP configuration |
| `Hospital_EIGRP_Config_Report.pdf` | EIGRP configuration |
| `Hospital_NAT.pdf` | NAT/PAT configuration |
| `CN Project Report.docx` | Complete project report |

---

## 👥 Project Team

| Student Name | Student ID |
|--------------|-----------|
| Sultan Mahmud Rasel | 241-15-521 |
| Md. Foridul Islam | 241-15-429 |
| Arpita Kundu | 241-15-143 |

## 🎓 Course Information

- **Course:** CSE322 – Computer Networks Lab
- **Department:** Computer Science and Engineering
- **University:** Daffodil International University
- **Location:** Dhaka, Bangladesh
- **Date:** 11 August 2026

## 👨‍🏫 Supervisor

**Mr. Tanvirul Islam**
Lecturer, Department of Computer Science and Engineering
Daffodil International University

## 🛠️ Project Implementation Flow

NETWORK DESIGN → VLSM / IP PLAN → VLAN CONFIGURATION → ACCESS PORTS
→ TRUNK CONFIG → ROUTER-ON-A-STICK → DHCP → EDGE–CORE LINKS
→ EIGRP (AS 100) → NAT/PAT → ISP NETWORK → INTERNET
→ HTTP / FTP / DNS / EMAIL → TESTING & VERIFICATION


## 📌 Final Project Summary

This project demonstrates the design and implementation of a multi-site smart hospital network using Cisco Packet Tracer. Through the combined use of VLSM, VLAN, Router-on-a-Stick, DHCP, EIGRP, NAT/PAT, and network services, the project provides structured departmental connectivity, dynamic routing, automatic IP configuration, inter-branch communication, and Internet access.

The complete Cisco Packet Tracer topology and supporting configuration documents are provided in this repository.
