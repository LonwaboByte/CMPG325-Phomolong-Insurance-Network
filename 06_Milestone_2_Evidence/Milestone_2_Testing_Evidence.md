# Milestone 2 – Testing Evidence

## 1. VLAN Verification

The VLAN configuration was verified on the switches using `show vlan brief`. The required VLANs were created and assigned according to the network design, including Management, Finance, Claims, Sales, Admin/HR, IT, Reception, Voice, Servers, Guest, Network Management and Future VLANs.

## 2. Trunk Verification

Trunk links between the switches and the Router-on-a-Stick connection were verified using `show interfaces trunk`. The required VLANs were active and forwarding across the trunk links.

## 3. Router-on-a-Stick Verification

R1 was configured with IEEE 802.1Q subinterfaces for the required VLANs. `show ip interface brief` confirmed that the physical interface and all configured VLAN subinterfaces were operational.

## 4. DHCP Testing

DHCP was tested across the required client VLANs. Staff and guest endpoints successfully received IP addresses, subnet masks, default gateways and DNS information from the configured DHCP services.

## 5. Inter-VLAN Routing

Inter-VLAN routing was tested between different departments and network services. For example, PC-FINANCE successfully communicated with the Web Server at `172.30.1.36`, receiving 4/4 replies with 0% packet loss.

## 6. Printer Connectivity

Connectivity to all five configured printers was tested from the network. The following printers were reachable:

- PRN-CLAIMS
- PRN-ADMIN
- PRN-SALES
- PRN-FINANCE
- PRN-MGMT

The tests confirmed that printer traffic could be routed between the relevant VLANs.

## 7. DNS and Web Server Testing

The DNS record `www.phomolong.local` was configured to resolve to the Web Server at `172.30.1.36`.

The hostname was successfully resolved from a staff workstation and the Web Server page was accessed successfully using the hostname.

## 8. Guest Wireless Testing

The guest laptop successfully connected to the `Phomolong-Guest` wireless network and received an address from the Guest VLAN.

The guest device could reach its own gateway but was prevented from accessing internal staff networks by the `GUEST_ISOLATION` ACL.

## 9. Guest Network Isolation

The guest laptop was tested against an internal staff endpoint. The connection was blocked by the configured ACL, confirming that Guest VLAN traffic was isolated from the internal `172.30.0.0/23` network while still allowing access to the guest gateway and DNS service.

## 10. VoIP Testing

The VoIP implementation was tested using the two configured IP phones.

- PHONE-FIRST was registered with extension 1001.
- PHONE-GROUND was registered with extension 1002.
- Both phones successfully registered with the R2-CME router.
- A test call from extension 1001 to extension 1002 was completed successfully.

The successful call confirmed that the Voice VLAN, DHCP voice configuration, CME registration and IP phone connectivity were functioning correctly.

## 11. Management Connectivity Testing

Management connectivity was tested using the Network Management VLAN (VLAN 110).

Connectivity between R1 and the management interfaces of SW1, SW2 and SW3 was verified successfully. This confirmed that the switches could communicate through the designated management network.

## 12. Final Testing Summary

The Milestone 2 network was tested after implementation. VLANs, trunk links, Router-on-a-Stick routing, DHCP, inter-VLAN connectivity, printer connectivity, DNS, web services, Guest network isolation, VoIP and management connectivity were verified.

The testing confirmed that the implemented network functions according to the Milestone 2 requirements and the documented design.
