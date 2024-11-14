# Cisco IOS Command Reference Guide

## Configuration Modes Navigation

| Command | Description |
|---------|-------------|
| `enable` | Enter privileged EXEC mode from user EXEC mode |
| `disable` | Return to user EXEC mode from privileged EXEC mode |
| `configure terminal` | Enter global configuration mode |
| `exit` | Exit current mode and return to previous mode |
| `end` | Return to privileged EXEC mode from any config mode |
| `Ctrl+Z` | Return to privileged EXEC mode from any config mode |
| `do` | Execute privileged commands from configuration mode |

## Interface Status and Configuration

| Command | Description |
|---------|-------------|
| `show interfaces status` | Displays status of all interfaces with speed, duplex, and VLAN info |
| `show interfaces ethernet x/y` | Shows detailed interface statistics and configuration |
| `show ip interface brief` | Quick view of IP addresses and status of all interfaces |
| `interface ethernet x/y` | Enters interface configuration mode |
| `shutdown` / `no shutdown` | Disables/enables the interface |
| `speed {10\|100\|1000\|auto}` | Sets interface speed |
| `duplex {full\|half\|auto}` | Sets duplex mode |
| `description STRING` | Adds description to interface |

## VLAN Configuration

| Command | Description |
|---------|-------------|
| `show vlan brief` | Displays list of all VLANs and their assigned ports |
| `show vlan id NUMBER` | Shows detailed information about specific VLAN |
| `vlan NUMBER` | Creates VLAN and enters VLAN config mode |
| `name STRING` | Assigns name to VLAN |
| `switchport mode {access\|trunk}` | Sets port mode |
| `switchport access vlan NUMBER` | Assigns port to VLAN |
| `switchport trunk allowed vlan {add\|remove} NUMBERS` | Modifies allowed VLANs on trunk |
| `show interfaces trunk` | Shows all trunk ports and their configuration |

## Port Channel Configuration

| Command | Description |
|---------|-------------|
| `show etherchannel summary` | Displays all port channels and their members |
| `show etherchannel detail` | Shows detailed port channel information |
| `interface port-channel NUMBER` | Creates/configures port channel interface |
| `channel-group NUMBER mode {active\|passive\|on}` | Adds interface to port channel |
| `show etherchannel load-balance` | Shows load-balancing method |
| `port-channel load-balance METHOD` | Configures load-balancing method |

## ARP and MAC Address Validation

| Command | Description |
|---------|-------------|
| `show arp` | Shows complete ARP table |
| `show ip arp INTERFACE` | Shows ARP entries for specific interface |
| `show mac address-table` | Displays complete MAC address table |
| `show mac address-table dynamic` | Shows only dynamically learned MAC addresses |
| `show mac address-table address MAC-ADDR` | Shows entries for specific MAC address |
| `show mac address-table vlan NUMBER` | Shows MAC addresses in specific VLAN |
| `clear arp-cache` | Clears ARP table |
| `clear mac address-table dynamic` | Clears dynamic MAC address entries |

## Troubleshooting and Validation

| Command | Description |
|---------|-------------|
| `show running-config interface INTERFACE` | Shows current interface configuration |
| `show interfaces counters` | Displays interface packet counters |
| `show interfaces ethernet x/y trunk` | Shows trunk configuration for specific interface |
| `show spanning-tree` | Displays STP information for all VLANs |
| `show cdp neighbors` | Shows directly connected Cisco devices |
| `show platform interface INTERFACE` | Shows platform-specific interface information |

## Configuration Management

| Command | Description |
|---------|-------------|
| `copy running-config startup-config` | Saves current configuration |
| `write memory` | Alternative command to save configuration |
| `show running-config` | Displays current configuration |
| `show startup-config` | Displays saved configuration |
| `erase startup-config` | Erases saved configuration |
