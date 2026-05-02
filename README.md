# Project--1-Labs

<img width="1316" height="869" alt="Topology-Proj#1" src="https://github.com/user-attachments/assets/e0d820e1-8f4d-48fb-b786-0bd052b3b919" />



# CCNA Project #1 – Basic Enterprise Network (Static Routing)

![CCNA](https://img.shields.io/badge/CCNA-Project-blue)
![Cisco](https://img.shields.io/badge/Cisco-Routing-red)

## 📌 Project Overview
This project simulates a basic enterprise network consisting of **two separate LANs** connected via **static routing** using Cisco routers.

The goal is to establish **end-to-end connectivity** between the HR and IT departments.

---

## 🏢 Business Scenario
A company has two departments:

- **LAN 1 – HR Department** → `192.168.10.0/24`
- **LAN 2 – IT Department** → `192.168.20.0/24`

---

## 🗺️ Network Topology

*(Ilagay dito ang topology diagram mo)*

![Network Topology](topology.png)  
<!-- Kapag may image ka na, palitan mo ito -->

---

## 🌐 IP Addressing Table

| Device | Interface   | IP Address      | Subnet Mask     | Default Gateway |
|--------|-------------|-----------------|-----------------|-----------------|
| R1     | G0/0        | 192.168.10.1    | 255.255.255.0   | N/A             |
| R1     | S0/0/0      | 10.0.0.1        | 255.255.255.252 | N/A             |
| R2     | S0/0/0      | 10.0.0.2        | 255.255.255.252 | N/A             |
| R2     | G0/0        | 192.168.20.1    | 255.255.255.0   | N/A             |
| PC1    | NIC         | 192.168.10.10   | 255.255.255.0   | 192.168.10.1    |
| PC2    | NIC         | 192.168.10.20   | 255.255.255.0   | 192.168.10.1    |
| PC3    | NIC         | 192.168.20.10   | 255.255.255.0   | 192.168.20.1    |
| PC4    | NIC         | 192.168.20.20   | 255.255.255.0   | 192.168.20.1    |

---

## ⚙️ Configuration

### 🔹 R1 Configuration

```cisco
interface g0/0
 ip address 192.168.10.1 255.255.255.0
 no shutdown

interface s0/0/0
 ip address 10.0.0.1 255.255.255.252
 no shutdown

ip route 192.168.20.0 255.255.255.0 10.0.0.2


### 🔹 R2 Configuration

interface g0/0
 ip address 192.168.20.1 255.255.255.0
 no shutdown

interface s0/0/0
 ip address 10.0.0.2 255.255.255.252
 no shutdown

ip route 192.168.10.0 255.255.255.0 10.0.0.1




🧪 Verification & Testing
Ping Test (From PC1 to PC3):
Bashping 192.168.20.10



Issues Encountered & Solutions
(Lagyan mo dito kung may naging problema ka)

Issue: No connectivity between LANs
Solution: Added correct static routes on both routers


📈 Conclusion
This project successfully demonstrates the configuration of a basic routed network using static routing. It strengthens foundational CCNA skills in network design, IP addressing, and routing.


### TO DO 
Upload the ping result here (Screenshot)
Upload CLI Config



👨‍💻 Author
Chanox – CCNA Trainee | Aspiring Network Engineer
