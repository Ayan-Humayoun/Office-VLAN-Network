#  Office VLAN Network Project

This project demonstrates how to configure a **Cisco Switch with VLANs** in Cisco Packet Tracer to simulate an office network.

##  Project Overview

The office has 3 departments:

* **HR** → VLAN 10
* **IT** → VLAN 20
* **Finance** → VLAN 30

Each department has 2 PCs connected to a central switch. VLANs logically separate the departments for security and traffic control.


##  Configuration Steps

1. **Create VLANs**

   ```bash
   Switch(config)# vlan 10
   Switch(config-vlan)# name HR
   Switch(config)# vlan 20
   Switch(config-vlan)# name IT
   Switch(config)# vlan 30
   Switch(config-vlan)# name Finance
   ```

2. **Assign Ports to VLANs**

   ```bash
   Switch(config)# interface range fastEthernet 0/1-2
   Switch(config-if-range)# switchport mode access
   Switch(config-if-range)# switchport access vlan 10

   Switch(config)# interface range fastEthernet 0/3-4
   Switch(config-if-range)# switchport mode access
   Switch(config-if-range)# switchport access vlan 20

   Switch(config)# interface range fastEthernet 0/5-6
   Switch(config-if-range)# switchport mode access
   Switch(config-if-range)# switchport access vlan 30
   ```

3. **Assign IP Addresses to PCs**

   * VLAN 10 (HR): `192.168.10.2/24`, `192.168.10.3/24`
   * VLAN 20 (IT): `192.168.20.2/24`, `192.168.20.3/24`
   * VLAN 30 (Finance): `192.168.30.2/24`, `192.168.30.3/24`

4. **Test Connectivity**

   * ✅ PCs in the **same VLAN** can ping each other.
   * ❌ PCs in **different VLANs** cannot communicate (without a router).

---

##  Future Work

* Add a **Router-on-a-Stick** for inter-VLAN communication.
* Implement **security features** like port security.

---

##  Files Included

* `Office-VLAN-switch-Project.pkt` → Packet Tracer simulation file
* `Network topology.png` → Network topology diagram
* `vlan_project_report.pdf` → Project report

---

##  Skills Learned

* VLAN creation and management
* Assigning switch ports to VLANs
* Subnetting per department
* Testing network isolation

---


