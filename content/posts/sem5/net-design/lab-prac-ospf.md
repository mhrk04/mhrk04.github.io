---
title: "Lab Practice - Configuring Basic Single-Area OSPFv2"
date: 2024-05-27T08:54:26+08:00
weight: 1
tags: ["CCNA", "Network Design", "OSPFv2", "Networking", "IFD20704"]
author: ["Haziq Rohaizan"]
description: "This is a lab practice guide for subject IFD20704 - NETWORK DESIGN. The lab will focus in Configuring Basic Single-Area OSPFv2 on Cisco based hardware. We will use Cisco Packet Tracer as simulation software."
showToc: true
TocOpen: true
draft: false
hidemeta: false
hideSummary: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
# cover:
#     image: "<image path/url>" # image path/url
#     alt: "<alt text>" # alt text
#     caption: "<text>" # display caption under cover
#     relative: false # when using page bundles set this to true
#     hidden: true # only hide on current single page
# editPost:
#     URL: "https://github.com/mhrk04/mhrk04.github.io/edit/main/content/"
#     Text: "Suggest Changes" # edit text
#     appendFilePath: true # to append file path to Edit link
---

## Topology

![topology](/img/net-design/ospf1-1.png)

> Cable the network as shown in the topology

## IP Address Table

| Device | Interface   | IP/Network Address | Subnet Mask       | Default Gateway |
|--------|-------------|---------------------|-------------------|-----------------|
| R1     | L0          | 209.165.10.1        | 255.255.255.0     | N/A             |
|        | G0/0        | 172.16.0.1          | 255.255.255.0     | N/A             |
|        | S0/0/0      | 192.168.10.2        | 255.255.255.252   | N/A             |
|        | S0/0/1      | 192.168.10.6        | 255.255.255.252   | N/A             |
| R2     | L5          | 200.100.11.1        | 255.255.255.192   | N/A             |
|        | L6          | 200.100.11.65       | 255.255.255.192   | N/A             |
|        | L7          | 200.100.11.129      | 255.255.255.224   | N/A             |
|        | G0/0.10     | 172.16.1.1          | 255.255.255.128   | N/A             |
|        | G0/0.20     | 172.16.1.129        | 255.255.255.192   | N/A             |
|        | S0/0/0      | 192.168.10.1        | 255.255.255.252   | N/A             |
|        | S0/0/1      | 192.168.10.9        | 255.255.255.252   | N/A             |
| R3     | L8          | 200.100.12.1        | 255.255.255.128   | N/A             |
|        | L9          | 200.100.12.129      | 255.255.255.192   | N/A             |
|        | L10         | 200.100.12.193      | 255.255.255.224   | N/A             |
|        | G0/0.30     | 172.16.2.1          | 255.255.255.192   | N/A             |
|        | G0/0.40     | 172.16.2.65         | 255.255.255.224   | N/A             |
|        | S0/0/0      | 192.168.10.10       | 255.255.255.252   | N/A             |
|        | S0/0/1      | 192.168.10.5        | 255.255.255.252   | N/A             |
| S1     | Int vlan 1  | 172.16.0.2          | 255.255.255.0     | N/A             |
| S2     | Int vlan 1  | 172.16.1.194        | 255.255.255.224   | N/A             |
| S3     | Int vlan 1  | 172.16.2.129        | 255.255.255.240   | N/A             |
| PC1    | NIC         | 172.16.1.3          | 255.255.255.128   | 172.16.1.1      |
| PC2    | NIC         | 172.16.1.131        | 255.255.255.192   | 172.16.1.129    |
| PC3    | NIC         | 172.16.2.3          | 255.255.255.192   | 172.16.2.1      |
| PC4    | NIC         | 172.16.2.67         | 255.255.255.224   | 172.16.2.65     |
| PC5    | NIC         | 172.16.0.4          | 255.255.255.0     | 172.16.0.1      |

## Device Configs

### R1 Configs

```
hostname R1
no ip domain-lookup
interface Loopback0
ip address 209.165.10.1 255.255.255.0

interface GigabitEthernet0/0
 ip address 172.16.0.1 255.255.255.0
 duplex auto
 speed auto
!
interface Serial0/0/0
 ip address 192.168.10.2 255.255.255.252
!
interface Serial0/0/1
 ip address 192.168.10.6 255.255.255.252
 clock rate 2000000

router ospf 1
 router-id 1.1.1.1
 log-adjacency-changes
 redistribute static subnets 
 passive-interface GigabitEthernet0/0
 network 192.168.10.0 0.0.0.3 area 0
 network 192.168.10.4 0.0.0.3 area 0
 network 172.16.0.0 0.0.0.255 area 0
 default-information originate
!
ip route 0.0.0.0 0.0.0.0 Loopback0 
```

### R2 Configs

```

hostname R2

no ip domain-lookup

interface Loopback5
 ip address 200.100.11.1 255.255.255.192
!
interface Loopback6
 ip address 200.100.11.65 255.255.255.192
!
interface Loopback7
 ip address 200.100.11.129 255.255.255.224
!
interface GigabitEthernet0/0
 no ip address
 duplex auto
 speed auto
!
interface GigabitEthernet0/0.10
 encapsulation dot1Q 10
 ip address 172.16.1.1 255.255.255.128
!
interface GigabitEthernet0/0.20
 encapsulation dot1Q 20
 ip address 172.16.1.129 255.255.255.192

interface Serial0/0/0
 ip address 192.168.10.1 255.255.255.252
 clock rate 2000000
!
interface Serial0/0/1
 ip address 192.168.10.9 255.255.255.252

router ospf 1
 router-id 2.2.2.2
 log-adjacency-changes
 passive-interface GigabitEthernet0/0
 network 192.168.10.0 0.0.0.3 area 0
 network 192.168.10.8 0.0.0.3 area 0
 network 200.100.11.0 0.0.0.255 area 0
 network 172.16.1.0 0.0.0.255 area 0

```

### R3 Configs

```
hostname R3

no ip domain-lookup
!
interface Loopback8
 ip address 200.100.12.1 255.255.255.128
!
interface Loopback9
 ip address 200.100.12.129 255.255.255.192
!
interface Loopback10
 ip address 200.100.12.193 255.255.255.224
!
interface GigabitEthernet0/0.30
 encapsulation dot1Q 30
 ip address 172.16.2.1 255.255.255.192
!
interface GigabitEthernet0/0.40
 encapsulation dot1Q 40
 ip address 172.16.2.65 255.255.255.224

interface Serial0/0/0
 ip address 192.168.10.10 255.255.255.252
 clock rate 2000000
!
interface Serial0/0/1
 ip address 192.168.10.5 255.255.255.252

router ospf 1
 router-id 3.3.3.3
 log-adjacency-changes
 passive-interface GigabitEthernet0/0
 network 192.168.10.4 0.0.0.3 area 0
 network 192.168.10.8 0.0.0.3 area 0
 network 200.100.12.0 0.0.0.255 area 0
 network 172.16.0.0 0.0.255.255 area 0
```

### S1 Configs

```
hostname S1
no ip domain-lookup

interface Vlan1
 ip address 172.16.0.2 255.255.255.0

```

### S2 Configs

```
hostname S2
no ip domain-lookup

interface FastEthernet0/5
 switchport access vlan 10
 switchport mode access
!
interface FastEthernet0/10
 switchport access vlan 20
 switchport mode access
!
interface GigabitEthernet0/1
 switchport mode trunk
interface Vlan1
 ip address 172.16.1.194 255.255.255.224
!
```

### S3 Configs

```
hostname S3
no ip domain-lookup
!
interface FastEthernet0/5
 switchport access vlan 30
 switchport mode access
!
interface FastEthernet0/10
 switchport access vlan 40
 switchport mode access
!
interface GigabitEthernet0/1
 switchport mode trunk

interface Vlan1
 ip address 172.16.2.129 255.255.255.240
```
