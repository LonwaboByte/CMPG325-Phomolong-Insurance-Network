# CMPG325 — Phomolong Insurance Brokers Network

## Project Overview

This repository contains the **CMPG 325 Computer Networks individual project** for **Phomolong Insurance Brokers, Vryburg**.

The project focuses on the design and implementation of a scalable departmental network using the assigned IPv4 address block:

`172.30.0.0/23`

The network design includes VLAN segmentation, VLSM addressing, Router-on-a-Stick inter-VLAN routing, DHCP, VoIP support, guest wireless access, internal servers, departmental printers, network management, and capacity for future expansion.

---

## Milestone 1 — Client Design Review

Milestone 1 focused on the initial network design and planning.

The milestone included:

* Client requirements and design assumptions
* Physical network topology
* Logical network topology
* VLSM IP addressing plan
* Initial GitHub portfolio structure

---

## Milestone 2 — Implementation & Testing

Milestone 2 focused on implementing and testing the approved network design in Cisco Packet Tracer.

The implemented network includes:

* Router-on-a-Stick inter-VLAN routing
* 12 VLANs
* VLAN gateways and router subinterfaces
* Trunk links between network devices
* Network Management VLAN 110
* DHCP services
* DHCP relay using `ip helper-address`
* Voice VLAN 80
* Cisco CME VoIP
* Guest wireless network
* Guest network isolation using an ACL
* DNS services
* Web Server
* Static network printers
* Inter-VLAN connectivity

---

## VLAN Structure

The network uses the following VLANs:

| VLAN | Department / Purpose |
| ---: | -------------------- |
|   10 | Management           |
|   20 | Finance              |
|   30 | Claims               |
|   40 | Sales                |
|   50 | Admin/HR             |
|   60 | IT                   |
|   70 | Reception            |
|   80 | Voice                |
|   90 | Servers              |
|  100 | Guest                |
|  110 | Network Management   |
|  120 | Future               |

---

## Routing and Addressing

The network uses **Router-on-a-Stick** to provide inter-VLAN routing.

The assigned IPv4 address block is:

`172.30.0.0/23`

VLANs are separated using VLSM addressing according to the network requirements.

DHCP is used for client address assignment, while DHCP relay is configured where required using:

`ip helper-address`

---

## VoIP — CR11

CR11 required the implementation of VoIP handsets for management.

The VoIP implementation includes:

* Voice VLAN 80
* Voice network `172.30.0.0/26`
* R2-CME for Cisco CallManager Express functionality
* DHCP option 150
* Extension 1001
* Extension 1002
* IP phone registration
* Successful test call between the two extensions

R2-CME was introduced because the original R1 Packet Tracer IOS did not support the required `telephony-service` functionality.

---

## Guest Wireless Network

A Guest wireless network was implemented using the Guest VLAN.

A guest laptop was used as a test endpoint to verify:

* Wireless connectivity
* DHCP address assignment
* Guest VLAN gateway connectivity
* DNS resolution
* Guest network isolation

The `GUEST_ISOLATION` ACL prevents the guest network from accessing internal staff networks while allowing the guest device to access the required guest services.

---

## Network Services

The implemented network includes:

* DHCP
* DNS
* Web Server
* Static network printers
* VoIP services
* Inter-VLAN routing
* Network management

The internal web service is available through the configured DNS name:

`www.phomolong.local`

---

## Testing

The implemented network was tested after configuration.

Testing covered:

* VLAN configuration
* Trunk connectivity
* Router-on-a-Stick operation
* DHCP address assignment
* Inter-VLAN routing
* Printer connectivity
* DNS resolution
* Web Server access
* Guest wireless connectivity
* Guest network isolation
* VoIP registration
* VoIP calling
* Network management connectivity

Detailed testing evidence is available in:

`06_Milestone_2_Evidence/Milestone_2_Testing_Evidence.md`

---

## Troubleshooting

Several implementation issues were identified and resolved during testing.

### SW3 Voice VLAN

The IP phone connected to SW3 initially did not have a Voice VLAN configured.

The issue was corrected using:

`switchport voice vlan 80`

### CME Support

The original R1 Packet Tracer IOS did not support the required `telephony-service` command.

R2-CME was therefore introduced to provide the required Cisco CME functionality.

### Guest ACL

The initial Guest isolation ACL prevented the guest device from reaching its own gateway.

The ACL was corrected to permit access to the Guest gateway while continuing to block internal networks.

### Guest DNS

The Guest laptop initially had an incorrect DNS configuration.

The DNS server was corrected to:

`172.30.1.34`

After the correction, `www.phomolong.local` resolved successfully.

---

## Repository Structure

```text
01_Client_Requirements/
02_Physical_Topology/
03_Logical_Topology/
04_IP_Addressing/
05_Milestone_1_Evidence/
06_Milestone_2_Evidence/
README.md
```

### Milestone 2 Evidence

The `06_Milestone_2_Evidence` folder contains:

```text
README.md
MILESTONE 2 FINAL TOPOLOGY.PNG
Milestone_2_Testing_Evidence.md
PHOMOLONG_MILESTONE_2_IMPLEMENTATION.pkt
```

---

## Packet Tracer Implementation

The final working Cisco Packet Tracer implementation is included in the Milestone 2 evidence folder.

The Packet Tracer file contains the implemented network topology, VLAN configuration, routing, DHCP, guest network, network services, printers and VoIP configuration.

---

## Project Technologies

* Cisco Packet Tracer
* Cisco IOS
* Router-on-a-Stick
* VLANs
* VLSM
* DHCP
* DHCP Relay
* ACLs
* DNS
* Web Services
* Cisco CME
* IP Telephony
* Wireless Networking
* IPv4 Networking

---

## Final Verification

The final Milestone 2 implementation was tested after configuration.

The testing confirmed the operation of the VLANs, trunk links, Router-on-a-Stick routing, DHCP, inter-VLAN connectivity, printers, DNS, Web Server, Guest network isolation, VoIP and network management.

The repository contains the project design documentation, implementation evidence, testing evidence and final working Packet Tracer file.
