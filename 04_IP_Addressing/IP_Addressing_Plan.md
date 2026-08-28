# IP Addressing Plan

## Phomolong Insurance Brokers — Vryburg

**Course:** CMPG 325 Computer Networks  
**Project:** Individual Network Design and Implementation  
**Client:** Phomolong Insurance Brokers  
**Location:** Vryburg  
**Assigned Address Block:** 172.30.0.0/23  
**Addressing Method:** Variable Length Subnet Masking (VLSM)

## Addressing Overview

The assigned IPv4 address block for the Phomolong Insurance Brokers network is **172.30.0.0/23**. The network is divided into separate VLAN subnets using **VLSM** to support the different departments, servers, voice traffic, guest wireless access, network management, and future expansion.

The first usable IP address in each VLAN subnet is reserved as the **default gateway** for Router-on-a-Stick inter-VLAN routing.

## VLAN and VLSM Addressing Plan

| VLAN | VLAN Name | Network Address | Prefix | Subnet Mask | Default Gateway | Usable Host Range | Broadcast Address |
|---:|---|---|:---:|---|---|---|---|
| 80 | VOICE | 172.30.0.0 | /26 | 255.255.255.192 | 172.30.0.1 | 172.30.0.1 – 172.30.0.62 | 172.30.0.63 |
| 120 | FUTURE | 172.30.0.64 | /26 | 255.255.255.192 | 172.30.0.65 | 172.30.0.65 – 172.30.0.126 | 172.30.0.127 |
| 100 | GUEST | 172.30.0.128 | /27 | 255.255.255.224 | 172.30.0.129 | 172.30.0.129 – 172.30.0.158 | 172.30.0.159 |
| 40 | SALES | 172.30.0.160 | /27 | 255.255.255.224 | 172.30.0.161 | 172.30.0.161 – 172.30.0.190 | 172.30.0.191 |
| 30 | CLAIMS | 172.30.0.192 | /27 | 255.255.255.224 | 172.30.0.193 | 172.30.0.193 – 172.30.0.222 | 172.30.0.223 |
| 20 | FINANCE | 172.30.0.224 | /28 | 255.255.255.240 | 172.30.0.225 | 172.30.0.225 – 172.30.0.238 | 172.30.0.239 |
| 50 | ADMIN_HR | 172.30.0.240 | /28 | 255.255.255.240 | 172.30.0.241 | 172.30.0.241 – 172.30.0.254 | 172.30.0.255 |
| 10 | MANAGEMENT | 172.30.1.0 | /28 | 255.255.255.240 | 172.30.1.1 | 172.30.1.1 – 172.30.1.14 | 172.30.1.15 |
| 60 | IT | 172.30.1.16 | /29 | 255.255.255.248 | 172.30.1.17 | 172.30.1.17 – 172.30.1.22 | 172.30.1.23 |
| 70 | RECEPTION | 172.30.1.24 | /29 | 255.255.255.248 | 172.30.1.25 | 172.30.1.25 – 172.30.1.30 | 172.30.1.31 |
| 90 | SERVERS | 172.30.1.32 | /29 | 255.255.255.248 | 172.30.1.33 | 172.30.1.33 – 172.30.1.38 | 172.30.1.39 |
| 110 | NET_MGMT | 172.30.1.40 | /29 | 255.255.255.248 | 172.30.1.41 | 172.30.1.41 – 172.30.1.46 | 172.30.1.47 |

### Reserved Address Space

**172.30.1.48 – 172.30.1.255** remains unallocated and available for future network growth.
