# University Networking System - Computer Communication & Networks Project

A comprehensive university-wide network simulation project designed and implemented using **Cisco Packet Tracer**. This project demonstrates practical networking concepts including dynamic routing, VLAN segmentation, access control, and network address translation for a multi-campus educational institution.

## 📡 Project Overview

The **University Networking System** simulates a robust network infrastructure connecting main and branch campuses with various departments. The network ensures seamless communication, resource sharing, and secure access while implementing industry-standard networking protocols and security measures.

## 🏛️ Network Architecture

### Campus Structure
- **Building A (Main Campus):** Administrative & Finance Departments
- **Building B (Main Campus):** Staff & Student Departments  
- **Branch Campus:** Staff & Student Divisions
- **IT Department:** Centralized servers and printers

<img width="962" height="454" alt="image" src="https://github.com/user-attachments/assets/de190b6e-87fe-462a-9bfa-28a6a61831a2" />


### Network Topology Components
- **Routers:** 4 routers (2621XM and 2811XM series) with dynamic routing
- **Switches:** Multiple Cisco 2960 switches with VLAN configuration
- **End Devices:** PCs distributed across all departments
- **Peripherals:** Printers and centralized servers
- **Cabling:** Ethernet (internal) and Serial (router interconnections)

## 🔧 Implemented Networking Features

### 1. Dynamic Routing (RIP)
- Configured RIP (Routing Information Protocol) on all routers
- Enables automatic route discovery between campuses
- Reduces manual configuration overhead
- Ensures fault tolerance and path optimization

### 2. VLAN Segmentation
- **Admin VLAN:** Departmental isolation for administrative staff
- **Finance VLAN:** Secure financial operations network
- **IT VLAN:** Centralized IT infrastructure
- **Branch Student VLAN:** Separate network for branch campus students
- Enhances security and reduces broadcast traffic

### 3. Access Control Lists (ACLs)
- Restricts specific IP addresses from accessing certain resources
- Applied to Admin and Finance department PCs
- Provides granular security controls
- Prevents unauthorized access to sensitive data

### 4. Network Address Translation (NAT)
- Static NAT configuration for IT department devices
- Conserves public IP addresses
- Enables external network access while maintaining internal security
- Maps internal IPs (18.0.0.x) to public IPs (50.0.0.x)

## 🖥️ Configuration Examples

### Router RIP Configuration
```cisco
Router(config)#router rip
Router(config-router)#network 11.0.0.0
Router(config-router)#network 10.0.0.0
Router(config-router)#network 13.0.0.0
```

### VLAN Configuration on Switch
```cisco
Switch(config)#vlan 3
Switch(config-vlan)#name FINANCE
Switch(config)#int range fa0/1-4
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 3
```

### ACL Configuration
```cisco
Router(config)#access-list 10 deny host 10.0.0.3
Router(config)#access-list 10 permit any
Router(config)#int s1/0
Router(config-if)#ip access-group 10 out
```

### NAT Configuration
```cisco
Router(config)#ip nat inside source static 18.0.0.2 50.0.0.2
Router(config)#ip nat inside source static 18.0.0.3 50.0.0.3
Router(config)#int fa0/0
Router(config-if)#ip nat inside
Router(config)#int s1/0
Router(config-if)#ip nat outside
```

## 📊 Testing & Validation

### Connectivity Tests
- **Successful pings** between all campus devices
- **VLAN isolation** verified through connectivity tests
- **ACL restrictions** confirmed by blocked ping attempts
- **NAT functionality** validated through address translation tables

### Performance Metrics
- **Latency:** Average round-trip times between 85-200ms
- **Success Rate:** 80-100% packet delivery across network
- **Scalability:** Supports up to 254 devices per subnet

## 🎯 Key Results

1. ✅ **Full Connectivity:** All departments can communicate across campuses
2. ✅ **Security Enforcement:** ACLs successfully restrict unauthorized access
3. ✅ **Network Segmentation:** VLANs provide logical department isolation
4. ✅ **External Access:** NAT enables controlled external communication
5. ✅ **Dynamic Routing:** RIP ensures automatic path optimization

## 📁 Project Files Included

- **Packet Tracer Project File** (.pkt) - Complete network simulation
- **Configuration Scripts** - All router and switch configurations
- **Network Documentation** - IP addressing scheme and topology details
- **Testing Reports** - Connectivity and performance validation

## 🔧 Tools Used

- **Cisco Packet Tracer 8.x** - Network simulation platform
- **Command Line Interface (CLI)** - Device configuration
- **IP Addressing Calculator** - Subnet planning
- **Network Protocol Analyzer** - Traffic monitoring

## 👥 Team Members

- **Hadiqa Mehmood** (02-235232-007)
- **Mahnoor Sharif** (02-235232-001)


## 📚 Academic Information

- **Course:** Computer Communication & Networks Lab (CSE-223)
- **Program:** BS(IT)
- **Semester:** Fall 2024
- **University:** Bahria University Karachi Campus
- **Department:** Computer Science
- **Instructor:** Sir Fahad Farooq

## 🚀 How to Use

1. Open the project in **Cisco Packet Tracer 8.0+**
2. Explore the network topology and device configurations
3. Test connectivity using ping commands between devices
4. Modify configurations to experiment with different scenarios
5. Use simulation mode to analyze packet flow and routing

## 📈 Future Enhancements

- Implement OSPF or EIGRP for more efficient routing
- Add DHCP server for automatic IP assignment
- Configure VPN for secure remote access
- Implement QoS for prioritizing academic traffic
- Add wireless access points for mobility
- Set up network monitoring and management tools

---

**⭐ A practical demonstration of enterprise networking concepts suitable for educational institutions and network engineering students.**
