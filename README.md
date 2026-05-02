# Enterprise Network Design with QoS, Security and Load Balancing

## 📄 Description
This project demonstrates an enterprise-level network designed using Cisco Packet Tracer. It integrates VLAN segmentation, inter-VLAN routing, dynamic routing using OSPF, QoS for traffic prioritization, port security, DHCP configuration, and secure remote access using VTY authentication.

The goal is to simulate a real-world network with efficient traffic management, security enforcement, and fault tolerance.

---

## 📌 Project Overview

This network includes:

- VLAN segmentation for different departments  
- Inter-VLAN routing (Router-on-a-Stick)  
- Dynamic routing using OSPF  
- Load balancing using Equal Cost Multi Path (ECMP)  
- QoS for prioritizing Voice, Video, and Transaction traffic  
- DHCP for automatic IP allocation  
- ACL for access control (Guest restrictions)  
- Port security on switch ports  
- Remote access using Telnet (VTY lines)

---

## 🛠️ Technologies Used

- Cisco Packet Tracer  
- OSPF (Open Shortest Path First)  
- DHCP (Dynamic Host Configuration Protocol)  
- ICMP (for testing traffic)  
- QoS using DSCP (EF, AF41)  
- Access Control Lists (ACL)

---

## ⚙️ How the Project Works

### 1. VLAN & Routing
- Network is divided into VLANs
- Router handles communication between VLANs using subinterfaces

### 2. DHCP
- Router assigns IP addresses dynamically to all VLANs

### 3. OSPF & Load Balancing
- Two equal-cost paths are configured
- OSPF selects both paths → enables load balancing
- If one link fails, traffic automatically reroutes

### 4. QoS (Quality of Service)
Traffic priority:
Voice (DSCP EF) > Video (DSCP AF41) > Transaction > Default

- Voice → highest priority (low delay)
- Video → high priority
- Transaction → normal priority
- ICMP used to simulate transaction traffic

### 5. Security

#### 🔐 ACL
- Guest users are restricted from accessing specific servers

#### 🔒 Port Security
- Only one device allowed per port
- Unauthorized device → port shutdown

#### 🌐 Authentication
- Remote login secured using username/password
- Configured on VTY lines (Telnet access)

---

## 🚀 How to Run the Project

### Step 1:
Open Cisco Packet Tracer

### Step 2:
Load the project file:
File → Open → Select .pkt file

---

### Step 3: Test Connectivity
From any PC:
- ping default gateway
- ping other VLAN device


---

### Step 4: Test QoS
Run continuous ping:
ping <destination IP> repeat 20

Then check:
show policy-map interface

---

### Step 5: Verify Load Balancing
show ip route
- Look for multiple paths with equal cost

---

### Step 6: Test Port Security
- Replace device on same port  
- Check:
  show port-security interface fa0/1

---

### Step 7: Test Remote Access
From PC:
telnet <router IP>

Login using configured credentials

---

## 📊 Important Commands
show ip route
show ip ospf interface
show policy-map interface
show running-config
show access-lists
show port-security


---

## 🎯 Features

- Dynamic routing with automatic failover  
- Load balancing using OSPF (ECMP)  
- Traffic prioritization using QoS  
- Network security using ACL & port security  
- Automatic IP allocation using DHCP  
- Remote router access using VTY authentication  

---

## 💬 Conclusion

This project demonstrates how multiple networking concepts integrate to form a scalable, secure, and efficient enterprise network. It reflects real-world scenarios including traffic prioritization, access control, and redundancy.

---

## 📌 Future Improvements

- Implement SSH instead of Telnet  
- Add firewall configurations  
- Enhance traffic simulation for real-time analysis  

