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

The two IP phones were successfully registered with the Cisco Call Manager Express service on R2-CME.

- PHONE-FIRST: Extension 1001
- PHONE-GROUND: Extension 1002

A test call from extension 1001 to extension 1002 was successfully completed, confirming VoIP call functionality.

## 11. Network Management Testing

Management connectivity was tested between the network devices using VLAN 110. The management interfaces on SW1-CORE, SW2-GROUND and SW3-FIRST successfully communicated with the R1 management gateway.

## 12. Final Verification

The final implementation was tested in Packet Tracer after configuration and troubleshooting. The tests confirmed VLAN operation, trunking, DHCP, Router-on-a-Stick inter-VLAN routing, printer connectivity, DNS and Web services, guest wireless access control and VoIP functionality.
