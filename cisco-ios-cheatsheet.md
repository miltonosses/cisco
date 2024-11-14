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
