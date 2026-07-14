# Cisco IOS Command Reference With Notes

This document provides a clean list of Cisco IOS commands with short notes explaining when to use each one.

```cmd
enable                               # Enter privileged EXEC mode
configure terminal                   # Enter global configuration mode
hostname R1                          # Set device hostname
enable password XXX                  # Set legacy enable password
service password-encryption          # Encrypt all plain-text passwords
enable secret XXX                    # Set secure encrypted enable password
int g0/1                             # Enter interface GigabitEthernet0/1
int range g0/1-5, 7-10               # Configure multiple interfaces at once
shutdown                             # Disable interface
no shutdown                          # Enable interface
exit                                 # Exit current mode
do show running-config               # View active configuration
do show startup-config               # View saved configuration
write                                # Save running-config to startup-config
write memory                         # Same as write
copy running-config startup-config   # Manual save
show int status                      # Interface status summary
show interfaces f0/1                 # Detailed interface info
do show int desc                     # Show interface descriptions

do show mac address-table                      # View MAC table
clear mac address-table dynamic                # Clear learned MACs
clear mac address-table dynamic interface g0/1 # Clear MACs on specific port

int range g0/0-3                # Select access ports
switchport mode access          # Set ports to access mode
switchport access vlan 10       # Assign VLAN 10
do show vlan br                 # Display VLAN brief

int g0/0                         # Select trunk port
switchport trunk encap dot1q     # Set trunk encapsulation to 802.1Q
switchport mode trunk            # Enable trunking
switchport trunk allowed vlan 10 # Allow VLAN 10 on trunk
switchport trunk native vlan 1001 # Set native VLAN
do show int trunk                # View trunk status
do show int g0/0 sw              # Show switchport details

enable                                   # Enter privileged mode
conf t                                   # Enter global config
int g0/0                                 # Select interface
ip add 10.x.x.x 255.0.0.0                # Assign IP address
description ##abc##                      # Add interface description
ip route 0.0.0.0 0.0.0.0 g0/1 192.x.x.x  # Default route
no shutdown                              # Enable interface
ip add 192.168.1.62 255.255.255.192      # Assign IP (secondary or replacement)
do show ip interface br                  # IP/interface summary
do show interface g0/0                   # Detailed interface info
do show ip route                         # View routing table
do show run | include ip address         # Filter running-config for IPs

default interface g0/0                   # Reset interface to default
ip routing                               # Enable Layer 3 routing
int g0/1                                 # Select routed port
no switchport                            # Convert to Layer 3 interface
int g0/0.20                              # Create subinterface for VLAN 20
encapsulation dot1q 20                   # Tag VLAN 20
encapsulation dot1q 20 native            # Set VLAN 20 as native (optional)
ip add 192.x.x.x 255.255.255.0           # Assign IP to SVI/subinterface
ip route 0.0.0.0 0.0.0.0 192.168.1.194   # Default route
do show ip int br                        # Layer 3 interface summary
do show int status                       # Interface status
```