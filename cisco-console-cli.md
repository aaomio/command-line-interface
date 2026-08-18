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

# ROUTER

## Privileged EXEC / Global Configuration

R1> enable                                         # Enter privileged EXEC mode
R1# configure terminal                             # Enter global configuration mode
R1(config)# hostname R1                            # Set device hostname

## Interface Configuration

R1(config)# int g0/0                               # Enter GigabitEthernet0/0
R1(config)# int gigabitethernet0/0                 # Full interface name

R1(config-if)# ip address 10.x.x.x 255.0.0.0       # Assign IPv4 address
R1(config-if)# no shutdown                         # Enable interface

R1(config-if)# ip address 192.168.1.62 255.255.255.192
                                                   # Assign IPv4 address with /26 mask

R1(config-if)# ip address dhcp                     # Obtain interface IP address using DHCP

R1(config-if)# ip helper-address 142.250.151.102   # Configure DHCP relay/helper address


## Static Default Route

R1(config)# ip route 0.0.0.0 0.0.0.0 g0/1 192.x.x.x
                                                   # Configure default static route
                                                   # g0/1 = exit interface
                                                   # 192.x.x.x = next-hop address


## DHCP Server

R1(config)# ip dhcp excluded-address 192.168.1.1 192.168.1.10
                                                   # Exclude addresses from DHCP allocation

R1(config)# ip dhcp pool Oracle                    # Create DHCP pool
R1(dhcp-config)# network 192.168.1.0 255.255.255.0 # Define DHCP network
R1(dhcp-config)# dns-server 8.8.8.8                # Specify DNS server
R1(dhcp-config)# domain-name Matrix.com            # Specify DNS domain
R1(dhcp-config)# default-router 192.168.1.1        # Specify default gateway
R1(dhcp-config)# lease DD HH MM                    # Configure DHCP lease duration


## DHCP Static / Manual Binding

R1(config)# ip dhcp pool HOST-01                   # Create DHCP pool for host
R1(dhcp-config)# host 192.168.1.254 255.255.255.0  # Assign fixed IP address to host
R1(dhcp-config)# client-identifier ABCD            # Identify DHCP client
R1(dhcp-config)# option 43 ip 192.168.30.20        # Configure DHCP option 43


## GRE Tunnel

R1(config)# interface Tunnel0                      # Create/select GRE Tunnel 0
R1(config-if)# tunnel source ISP-int               # Specify tunnel source interface
R1(config-if)# tunnel destination ISP-IP           # Specify remote tunnel endpoint
R1(config-if)# ip address 10.10.10.1 255.255.255.252
                                                   # Assign tunnel IP address
R1(config-if)# no shutdown                         # Enable GRE tunnel

# Bootloader / ROMMON

: flash_init                                # Initialise flash filesystem
: dir usb:                                  # View files on USB
: dir flash:                                # View files in flash

: tar -xtract usb:<image>.tar flash:        # Extract TAR IOS image into flash
: copy usb:<file> flash:                    # Copy file from USB to flash

: dir flash:                                # Verify files in flash

: set BOOT flash:/<directory>/<IOS-image>   # Set BOOT variable to IOS image
: set                                       # Display environment variables
: boot                                      # Boot IOS image