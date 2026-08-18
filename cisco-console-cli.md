# Cisco IOS CLI

A structured reference of common Cisco IOS commands for switches, routers, and APs.

---
# Cisco IOS Command Reference 

# SWITCH

## Privileged EXEC / Global Configuration

SW1> enable                                       # Enter privileged EXEC mode
SW1# configure terminal                           # Enter global configuration mode
SW1(config)# hostname SW1                         # Set device hostname

SW1(config)# enable password XXX                  # Legacy enable password
SW1(config)# service password-encryption          # Encrypt plain-text passwords
SW1(config)# enable secret XXX                    # Encrypted enable password


## Interface Selection

SW1(config)# int g0/1                             # Enter interface GigabitEthernet0/1
SW1(config)# int range g0/0-3                     # Select multiple interfaces
SW1(config-if)# exit                              # Exit interface configuration mode


## VLAN — Access Port

SW1(config)# int range g0/0-3                     # Select multiple interfaces
SW1(config-if-range)# switchport mode access      # Force interfaces into access mode
SW1(config-if-range)# switchport access vlan 10   # Assign interfaces to VLAN 10


## Trunk Port

SW1(config)# int g0/0                             # Select trunk interface
SW1(config-if)# switchport trunk encapsulation dot1q
                                                  # Set 802.1Q encapsulation
SW1(config-if)# switchport mode trunk             # Force interface into trunk mode
SW1(config-if)# switchport trunk allowed vlan 10  # Allow VLAN 10 across trunk
SW1(config-if)# switchport trunk native vlan 1001 # Set VLAN 1001 as native VLAN


## Layer 3 / Routed Switch Port

SW1(config)# int g0/0                             # Select interface
SW1(config-if)# no switchport                     # Convert switchport into Layer 3 interface


## SVI — Switched Virtual Interface

SW1(config)# vlan 20                               # Create VLAN 20
SW1(config-vlan)# name USERS                       # Name VLAN 20
SW1(config-vlan)# exit                             # Exit VLAN configuration mode

SW1(config)# interface vlan 20                     # Create/select SVI for VLAN 20
SW1(config-if)# ip address 192.168.20.1 255.255.255.0
                                                   # Assign Layer 3 address to SVI
SW1(config-if)# no shutdown                        # Enable SVI

SW1(config)# ip routing                            # Enable Layer 3 routing
SW1(config)# ip route 0.0.0.0 0.0.0.0 192.168.1.194
                                                   # Configure default static route


## Port Security

SW1(config)# int g0/1                              # Select access port
SW1(config-if)# switchport mode access             # Port must be in access mode
SW1(config-if)# switchport port-security           # Enable port security

SW1(config-if)# switchport port-security mac-address FFFF.FFFF.FFFF
                                                   # Manually configure secure MAC address

SW1(config-if)# switchport port-security mac-address sticky
                                                   # Dynamically learn and secure MAC address