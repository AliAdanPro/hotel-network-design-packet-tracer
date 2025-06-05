# 🏨 Hotel Management Network Design & Implementation

This project is a simulation of an enterprise-level hotel network using **Cisco Packet Tracer**. It demonstrates core networking concepts such as VLANs, Inter-VLAN Routing, DHCP, Port Security, OSPF, SSH, and wireless integration.

---

## 📁 Project Overview

### 🏢 Hotel Structure:
- **3 Floors** (1st, 2nd, 3rd)
- **Multiple Departments** across VLANs:

| VLAN | Subnet           | Department   | Floor      |
|------|------------------|--------------|------------|
| 10   | 192.168.1.0/24   | IT           | 3rd Floor  |
| 20   | 192.168.2.0/24   | Admin        | 3rd Floor  |
| 30   | 192.168.3.0/24   | Sales        | 2nd Floor  |
| 40   | 192.168.4.0/24   | HR           | 2nd Floor  |
| 50   | 192.168.5.0/24   | Finance      | 2nd Floor  |
| 60   | 192.168.6.0/24   | Logistics    | 1st Floor  |
| 70   | 192.168.7.0/24   | Store        | 1st Floor  |
| 80   | 192.168.8.0/24   | Reception    | 1st Floor  |

---

## 🛠️ Key Technologies Implemented

### 🔹 VLANs
- Created on each floor's switch to segment departments.
- Trunk links used between router and switch to allow inter-VLAN traffic.

### 🔹 Inter-VLAN Routing
- **Router-on-a-Stick** configuration using sub-interfaces.

### 🔹 IP Addressing
- Each VLAN uses a **/24 subnet**.
- Router-to-router links use **/30 subnets** for efficiency:
  - 10.10.10.0/30, 10.10.10.4/30, 10.10.10.8/30

### 🔹 DHCP Configuration
- Each router serves DHCP for its directly connected VLANs.

### 🔹 OSPF (Open Shortest Path First)
- Configured on all 3 routers for dynamic routing between floors.
- Area 0 used to keep things simple.

### 🔹 SSH Configuration
- SSH enabled for secure remote access to all routers.

### 🔹 Port Security
- Applied to IT switch (port `fa0/1`) using **sticky MAC**:
  - Only allows **Test-PC** to connect
  - **Violation mode:** `shutdown`

---

## 📶 Wireless Integration
- Each floor has an Access Point.
- Laptops, smartphones, and tablets connect wirelessly.

---

## 💻 Demo Highlights

### ✅ Inter-VLAN Communication
- Devices from different VLANs on the same floor can communicate via router.

### ✅ Inter-Floor Routing
- Routers share routes using OSPF, enabling cross-floor communication.

### ✅ Port Security Test
- If a device other than Test-PC connects to port fa0/1, the port shuts down.

---

## 📷 Screenshots

<p align="center">
  <img src="https://github.com/user-attachments/assets/8fa89f32-3e1d-4eb9-b9ee-60c275d97ea5" alt="Network Topology" width="800"/>
</p>

---

## 🎓 Learning Objectives

- VLAN creation and trunking
- Router-on-a-stick for inter-VLAN
- DHCP and static IP planning
- OSPF routing across multiple routers
- Securing access with SSH and port security

---

## 📝 Tips
- Intra-VLAN = switch handles it
- Inter-VLAN = router handles it
- Port security = only specific MAC allowed
- OSPF = lets routers auto-learn routes

---

## ✅ Conclusion
This project demonstrates how to design and implement a secure, segmented, and scalable enterprise network using Packet Tracer. By applying concepts like VLANs, OSPF, SSH, and port security, it simulates real-world networking practices suitable for a hotel environment. It also provides hands-on experience in configuring both wired and wireless devices in a structured network setup.
