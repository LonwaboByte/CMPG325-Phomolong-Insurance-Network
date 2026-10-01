# Milestone 2 – Implementation & Testing Evidence

This folder contains implementation, configuration, testing, and troubleshooting evidence for Milestone 2 of the Phomolong Insurance Brokers network project.

## 1. Implementation Summary

The Milestone 2 network was implemented in Cisco Packet Tracer according to the approved network design.

The implementation includes:

* Router-on-a-Stick inter-VLAN routing
* 12 VLANs
* VLAN gateways and router subinterfaces
* Trunk links between network devices
* Switch management using VLAN 110
* DHCP services for network clients
* DHCP relay using `ip helper-address`
* Voice VLAN 80
* Cisco CME VoIP implementation
* Guest wireless network
* Guest network isolation using an ACL
* DNS and Web Server services
* Static network printers
* Inter-VLAN connectivity

## 2. CR11 – VoIP Implementation

CR11 required the implementation of VoIP handsets for management.

The following were implemented:

* Voice VLAN 80
* Voice addressing using the `172.30.0.0/26` network
* R2-CME for Cisco CallManager Express functionality
* DHCP option 150 for IP phone configuration
* IP phone extension 1001
* IP phone extension 1002
* Successful registration of both IP phones
* Successful test call between the two extensions

R2-CME was introduced because the original R1 Packet Tracer IOS did not support the required `telephony-service` functionality.

## 3. Guest Network Implementation

A guest wireless network was implemented using the existing Guest VLAN.

A guest laptop was added as a test endpoint to verify the Guest network configuration.

The guest endpoint:

* Connected to the `Phomolong-Guest` wireless network
* Received an IP address through DHCP
* Reached the Guest VLAN gateway
* Successfully resolved the configured DNS service
* Was prevented from accessing internal staff networks through the `GUEST_ISOLATION` ACL

## 4. Testing Evidence

The implemented network was tested to verify:

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
* VoIP registration and calling
* Management connectivity

Detailed testing evidence is provided in:

`Milestone_2_Testing_Evidence.md`

## 5. Troubleshooting

Several implementation issues were identified and resolved during testing.

### Issue 1 – SW3 Voice VLAN

The IP phone connected to SW3 initially did not have a Voice VLAN configured.

The issue was corrected by configuring:

`switchport voice vlan 80`

The phone subsequently received its voice configuration successfully.

### Issue 2 – CME Support

The original R1 Packet Tracer IOS did not support the required `telephony-service` command.

R2-CME was therefore introduced to provide the required Cisco CME functionality.

### Issue 3 – Guest ACL

The initial Guest isolation ACL prevented the guest device from reaching its own gateway.

The ACL was corrected to permit access to the Guest gateway while continuing to block access to internal networks.

### Issue 4 – Guest DNS

The Guest laptop initially had an incorrect DNS configuration.

The DNS server was corrected to:

`172.30.1.34`

After the correction, `www.phomolong.local` resolved successfully.

## 6. Milestone 2 Implementation Changes

Two notable additions were made during Milestone 2:

### R2-CME

R2-CME was added to support the CR11 VoIP requirement because the original R1 Packet Tracer IOS did not provide the required CME functionality.

### LAPTOP-GUEST

LAPTOP-GUEST was added as a temporary test endpoint to verify the existing Guest VLAN, wireless connectivity, DHCP configuration and Guest isolation ACL.

## 7. Evidence Files

This folder contains the following evidence:

* `README.md` – Milestone 2 implementation and testing overview
* `Milestone_2_Final_Topology.png` – Final Packet Tracer topology
* `Milestone_2_Testing_Evidence.md` – Detailed testing evidence

## 8. Final Verification

The Milestone 2 implementation was tested after configuration.

The testing confirmed the operation of the VLANs, trunk links, Router-on-a-Stick routing, DHCP, inter-VLAN connectivity, printers, DNS, Web Server, Guest network isolation, VoIP and management connectivity.

The final Packet Tracer implementation is documented through the accompanying topology and testing evidence.
