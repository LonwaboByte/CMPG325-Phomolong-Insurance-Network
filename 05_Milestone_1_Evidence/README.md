# Milestone 1 — Client Design Review

## Phomolong Insurance Brokers — Vryburg

This folder provides a summary of the evidence prepared for the CMPG 325 Milestone 1 Client Design Review.

## Milestone 1 Deliverables

| Deliverable | Location | Status |
|---|---|---|
| Client Requirements | `01_Client_Requirements/` | Complete |
| Physical Topology | `02_Physical_Topology/` | Complete |
| Logical Topology | `03_Logical_Topology/` | Complete |
| IP Addressing Plan | `04_IP_Addressing/` | Complete |
| Initial GitHub Repository | Repository Root | Complete |

## Design Overview

The proposed network for Phomolong Insurance Brokers uses the assigned `172.30.0.0/23` IPv4 address block and VLSM to provide addressing for departmental, voice, server, guest, network-management and future-expansion VLANs.

The design uses a Cisco 2911 router with Router-on-a-Stick planned for inter-VLAN routing. A central core switch connects to separate Ground Floor and First Floor access switches. VLAN 80 accommodates the VoIP requirement, while VLAN 120 and dedicated address capacity are reserved for the future second-floor expansion.

## Milestone 1 Status

**Client Design Review — Complete**

The network design is ready to proceed to Milestone 2 implementation and testing in Cisco Packet Tracer.
