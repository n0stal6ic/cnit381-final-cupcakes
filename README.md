# CNIT 381 – Network Automation Final Project  
## Network Automation with Ansible  
Fall 2025

---

# Project Overview
This project automates the configuration of a 2-router and 1-switch Cisco network using Ansible.  
Our automation covers base configuration, EIGRP routing, VLANs, network services, verification,  
and configuration backup. A management network connects the Ansible control node to all devices.

---

# Team Members
- Bryce
- Owen

---

# Repository Structure
network-automation-final/
├── README.md
├── ansible.cfg
├── inventory.ini
├── playbooks/
│ ├── 01_verify_connectivity.yml
│ ├── 02_base_config.yml
│ ├── 03_eigrp_config.yml
│ ├── 04_vlan_config.yml
│ ├── 05_services_config.yml
│ └── 06_backup_config.yml
├── backups/
└── documentation/
├── network_diagram.pdf
└── testing_results.md

# Network Topology
Our topology consists of:
- **Router1** (IOSv)
- **Router2** (IOSv)
- **Switch1** (IOSv-L2)
- **Ansible Control Node**

Key Technologies:
- EIGRP
- VLANs
- Trunking
- Router-on-a-stick
- NTP + Logging services  

The complete diagram is located in:  
`documentation/network_diagram.pdf`

---

# How to Run the Playbooks

### **1. Verify Connectivity**


ansible-playbook playbooks/01_verify_connectivity.yml


### **2. Base Configuration**


ansible-playbook playbooks/02_base_config.yml


### **3. EIGRP Configuration**


ansible-playbook playbooks/03_eigrp_config.yml


### **4. VLAN & Trunk Configuration**


ansible-playbook playbooks/04_vlan_config.yml


### **5. Network Services (NTP & Logging)**


ansible-playbook playbooks/05_services_config.yml


### **6. Backup Device Configurations**


ansible-playbook playbooks/06_backup_config.yml


Backups will be saved automatically in the `backups/` directory.

---

# Playbook Descriptions

### **01 — Verify Connectivity**
Tests SSH reachability of all devices.

### **02 — Base Config**
Applies hostnames, interface descriptions, and login banners.

### **03 — EIGRP Config**
Creates loopback interfaces, enables EIGRP, and advertises connected networks.

### **04 — VLAN Config**
Creates VLANs, configures switch trunk port, and sets up router subinterfaces.

### **05 — Services Config**
Sets NTP and logging buffered size.

### **06 — Backup Config**
Retrieves and stores each device's running configuration.

---

# Testing
Screenshots are stored in:
documentation/testing_results.md

---

# Lessons Learned
- We learned how to automate network configurations using ansible instad of manually configuring each network device.

---

# ✅