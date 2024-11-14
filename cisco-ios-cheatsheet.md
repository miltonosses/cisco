# Cisco IOS Command Reference Guide

## Configuration Modes Navigation

| Command | Description | Example |
|---------|-------------|----------|
| `enable` | Enter privileged EXEC mode from user EXEC mode | `Switch> enable` |
| `disable` | Return to user EXEC mode from privileged EXEC mode | `Switch# disable` |
| `configure terminal` | Enter global configuration mode | `Switch# configure terminal` |
| `exit` | Exit current mode and return to previous mode | `Switch(config-if)# exit` |
| `end` | Return to privileged EXEC mode from any config mode | `Switch(config-if)# end` |
| `do` | Execute privileged commands from configuration mode | `Switch(config)# do show run` |

## Interface Status and Configuration

| Command | Description | Example |
|---------|-------------|----------|
| `show interfaces status` | Displays status of all interfaces | `Switch# show interfaces status` |
| `show interfaces ethernet x/y` | Shows interface statistics | `Switch# show interfaces gi1/0/1` |
| `show ip interface brief` | Quick view of IP addresses | `Switch# show ip interface brief` |
| `interface ethernet x/y` | Enters interface configuration mode | `Switch(config)# interface gi1/0/1` |
| `shutdown` / `no shutdown` | Disables/enables the interface | `Switch(config-if)# no shutdown` |
| `speed {10\|100\|1000\|auto}` | Sets interface speed | `Switch(config-if)# speed 1000` |
| `duplex {full\|half\|auto}` | Sets duplex mode | `Switch(config-if)# duplex full` |
| `description STRING` | Adds description to interface | `Switch(config-if)# description UserPort` |

## VLAN Configuration

| Command | Description | Example |
|---------|-------------|----------|
| `show vlan brief` | Displays list of all VLANs | `Switch# show vlan brief` |
| `show vlan id NUMBER` | Shows specific VLAN info | `Switch# show vlan id 10` |
| `vlan NUMBER` | Creates VLAN and enters VLAN mode | `Switch(config)# vlan 10` |
| `name STRING` | Assigns name to VLAN | `Switch(config-vlan)# name HR-DEPT` |
| `switchport mode {access\|trunk}` | Sets port mode | `Switch(config-if)# switchport mode trunk` |
| `switchport access vlan NUMBER` | Assigns port to VLAN | `Switch(config-if)# switchport access vlan 10` |
| `switchport trunk allowed vlan` | Modifies allowed VLANs on trunk | `Switch(config-if)# switchport trunk allowed vlan 10,20` |
| `show interfaces trunk` | Shows trunk ports configuration | `Switch# show interfaces trunk` |

## Port Channel Configuration

| Command | Description | Example |
|---------|-------------|----------|
| `show etherchannel summary` | Displays all port channels | `Switch# show etherchannel summary` |
| `show etherchannel detail` | Shows detailed port channel info | `Switch# show etherchannel detail` |
| `interface port-channel NUMBER` | Creates port channel interface | `Switch(config)# interface port-channel 1` |
| `channel-group NUMBER mode` | Adds interface to port channel | `Switch(config-if)# channel-group 1 mode active` |
| `show etherchannel load-balance` | Shows load-balancing method | `Switch# show etherchannel load-balance` |
| `port-channel load-balance` | Sets load-balancing method | `Switch(config)# port-channel load-balance src-dst-ip` |

## ARP and MAC Address Validation

| Command | Description | Example |
|---------|-------------|----------|
| `show arp` | Shows complete ARP table | `Switch# show arp` |
| `show ip arp INTERFACE` | Shows interface ARP entries | `Switch# show ip arp vlan 1` |
| `show mac address-table` | Shows MAC address table | `Switch# show mac address-table` |
| `show mac address-table dynamic` | Shows dynamic MAC addresses | `Switch# show mac address-table dynamic` |
| `show mac address-table address` | Shows specific MAC address | `Switch# show mac address-table address 1234.5678.9abc` |
| `show mac address-table vlan` | Shows VLAN MAC addresses | `Switch# show mac address-table vlan 10` |
| `clear arp-cache` | Clears ARP table | `Switch# clear arp-cache` |
| `clear mac address-table dynamic` | Clears dynamic MAC entries | `Switch# clear mac address-table dynamic` |

## Troubleshooting and Validation

| Command | Description | Example |
|---------|-------------|----------|
| `show running-config interface` | Shows interface config | `Switch# show running-config interface gi1/0/1` |
| `show interfaces counters` | Shows interface counters | `Switch# show interfaces counters` |
| `show interfaces trunk` | Shows trunk configuration | `Switch# show interfaces trunk` |
| `show spanning-tree` | Shows STP information | `Switch# show spanning-tree vlan 10` |
| `show cdp neighbors` | Shows connected devices | `Switch# show cdp neighbors` |
| `show platform interface` | Shows platform interface info | `Switch# show platform interface gi1/0/1` |

## Configuration Management

| Command | Description | Example |
|---------|-------------|----------|
| `copy running-config startup-config` | Saves current configuration | `Switch# copy running-config startup-config` |
| `write memory` | Alternative save command | `Switch# write memory` |
| `show running-config` | Shows current config | `Switch# show running-config` |
| `show startup-config` | Shows saved config | `Switch# show startup-config` |
| `erase startup-config` | Erases saved config | `Switch# erase startup-config` |


# Cisco IOS Layer 3 and Routing Protocols Configuration Guide

## Layer 3 Interface Configuration

| Command | Description | Example |
|---------|-------------|----------|
| `no switchport` | Convert interface to Layer 3 | `Switch(config-if)# no switchport` |
| `ip address IP_ADDR MASK` | Configure IP address | `Switch(config-if)# ip address 192.168.1.1 255.255.255.0` |
| `ip address IP_ADDR MASK secondary` | Add secondary IP | `Switch(config-if)# ip address 192.168.2.1 255.255.255.0 secondary` |
| `ip helper-address IP_ADDR` | Configure DHCP relay | `Switch(config-if)# ip helper-address 10.1.1.100` |
| `show ip interface` | Verify L3 interface status | `Switch# show ip interface gi1/0/1` |
| `show ip route` | View routing table | `Switch# show ip route` |

## VRF (Virtual Routing and Forwarding)

| Command | Description | Example |
|---------|-------------|----------|
| `vrf definition NAME` | Create VRF | `Switch(config)# vrf definition CUSTOMER_A` |
| `address-family ipv4` | Configure IPv4 address-family | `Switch(config-vrf)# address-family ipv4` |
| `ip vrf NAME` | Create VRF (old syntax) | `Switch(config)# ip vrf CUSTOMER_A` |
| `vrf forwarding NAME` | Assign interface to VRF | `Switch(config-if)# vrf forwarding CUSTOMER_A` |
| `show vrf` | Display VRF information | `Switch# show vrf` |
| `show ip route vrf NAME` | Show VRF routing table | `Switch# show ip route vrf CUSTOMER_A` |

## BGP (Border Gateway Protocol)

| Command | Description | Example |
|---------|-------------|----------|
| `router bgp AS_NUMBER` | Enable BGP routing | `Switch(config)# router bgp 65001` |
| `neighbor IP_ADDR remote-as AS` | Configure BGP peer | `Switch(config-router)# neighbor 10.1.1.2 remote-as 65002` |
| `network NETWORK mask MASK` | Advertise network | `Switch(config-router)# network 192.168.1.0 mask 255.255.255.0` |
| `address-family ipv4 vrf NAME` | Configure VRF-aware BGP | `Switch(config-router)# address-family ipv4 vrf CUSTOMER_A` |
| `show ip bgp summary` | Show BGP peers status | `Switch# show ip bgp summary` |
| `show ip bgp neighbors` | Show detailed peer info | `Switch# show ip bgp neighbors` |

## ECMP (Equal-Cost Multi-Path)

| Command | Description | Example |
|---------|-------------|----------|
| `maximum-paths NUMBER` | Configure ECMP paths | `Switch(config-router)# maximum-paths 8` |
| `ip route NETWORK MASK NEXT_HOP` | Create static route | `Switch(config)# ip route 10.0.0.0 255.255.255.0 192.168.1.1` |
| `ip route NETWORK MASK NEXT_HOP2` | Create additional equal path | `Switch(config)# ip route 10.0.0.0 255.255.255.0 192.168.2.1` |
| `show ip route NETWORK` | Verify ECMP routes | `Switch# show ip route 10.0.0.0` |

## VRRP (Virtual Router Redundancy Protocol)

| Command | Description | Example |
|---------|-------------|----------|
| `vrrp GROUP ip IP_ADDR` | Configure VRRP group | `Switch(config-if)# vrrp 1 ip 192.168.1.254` |
| `vrrp GROUP priority PRIORITY` | Set VRRP priority | `Switch(config-if)# vrrp 1 priority 150` |
| `vrrp GROUP preempt` | Enable preemption | `Switch(config-if)# vrrp 1 preempt` |
| `show vrrp` | Show VRRP status | `Switch# show vrrp` |
| `show vrrp brief` | Show VRRP summary | `Switch# show vrrp brief` |

## RIP (Routing Information Protocol)

| Command | Description | Example |
|---------|-------------|----------|
| `router rip` | Enable RIP routing | `Switch(config)# router rip` |
| `version 2` | Configure RIP version 2 | `Switch(config-router)# version 2` |
| `network NETWORK` | Define networks to advertise | `Switch(config-router)# network 192.168.1.0` |
| `no auto-summary` | Disable auto summarization | `Switch(config-router)# no auto-summary` |
| `ip rip authentication mode md5` | Enable MD5 authentication | `Switch(config-if)# ip rip authentication mode md5` |
| `ip rip authentication key-chain NAME` | Set authentication key | `Switch(config-if)# ip rip authentication key-chain RIP-KEY` |
| `passive-interface INTERFACE` | Stop RIP on interface | `Switch(config-router)# passive-interface gi1/0/1` |
| `default-information originate` | Advertise default route | `Switch(config-router)# default-information originate` |
| `show ip rip database` | Show RIP routes | `Switch# show ip rip database` |
| `show ip protocols` | Verify RIP configuration | `Switch# show ip protocols` |
| `debug ip rip` | Debug RIP updates | `Switch# debug ip rip` |

## OSPF (Open Shortest Path First)

| Command | Description | Example |
|---------|-------------|----------|
| `router ospf PROCESS_ID` | Enable OSPF routing | `Switch(config)# router ospf 1` |
| `network NETWORK WILDCARD area AREA` | Define OSPF networks | `Switch(config-router)# network 192.168.1.0 0.0.0.255 area 0` |
| `ip ospf cost COST` | Set interface OSPF cost | `Switch(config-if)# ip ospf cost 100` |
| `show ip ospf` | Show OSPF process | `Switch# show ip ospf` |
| `show ip ospf neighbor` | Show OSPF neighbors | `Switch# show ip ospf neighbor` |

## Route Maps and Policy

| Command | Description | Example |
|---------|-------------|----------|
| `route-map NAME permit SEQ` | Create route map | `Switch(config)# route-map FILTER permit 10` |
| `match ip address ACL` | Match IP prefix | `Switch(config-route-map)# match ip address prefix-list ALLOW` |
| `set local-preference VALUE` | Set BGP local preference | `Switch(config-route-map)# set local-preference 200` |
| `ip prefix-list NAME` | Create prefix list | `Switch(config)# ip prefix-list ALLOW permit 192.168.0.0/24` |
| `show route-map` | Show route maps | `Switch# show route-map FILTER` |

## Verification and Troubleshooting

| Command | Description | Example |
|---------|-------------|----------|
| `show ip protocols` | Show routing protocols | `Switch# show ip protocols` |
| `show ip route summary` | Show routing table summary | `Switch# show ip route summary` |
| `show ip bgp vpnv4 vrf NAME` | Show VRF BGP routes | `Switch# show ip bgp vpnv4 vrf CUSTOMER_A` |
| `traceroute vrf NAME` | VRF traceroute | `Switch# traceroute vrf CUSTOMER_A 8.8.8.8` |
| `ping vrf NAME` | VRF ping | `Switch# ping vrf CUSTOMER_A 192.168.1.1` |

