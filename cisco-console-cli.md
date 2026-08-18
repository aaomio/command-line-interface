# Cisco IOS CLI

A structured reference of common Cisco IOS commands for switches, routers, and APs.

---
# Cisco IOS Command Reference 

# SWITCH

## Privileged EXEC / Global Configuration

Switch> enable                        # Enter privileged EXEC mode
Switch# configure terminal            # Enter global configuration mode
switch(config)# hostname SW1          # Set device hostname

switch(config)# enable password XXX   # Legacy enable password
switch(config)# service password-encryption
                                      # Encrypt plain-text passwords
switch(config)# enable secret XXX     # Encrypted enable password

## Interface Selection

switch(config)# int g0/1              # Enter interface GigabitEthernet0/1
switch(config)# int range g0/0-3      # Select multiple interfaces
switch(config-if)# exit               # Exit interface configuration mode

## VLAN — Access Port

switch(config)# int range g0/0-3      # Select multiple interfaces
switch(config-if-range)# switchport mode access
                                      # Force interfaces into access mode
switch(config-if-range)# switchport access vlan 10
                                      # Assign interfaces to VLAN 10

## Trunk Port

switch(config)# int g0/0              # Select trunk interface
switch(config-if)# switchport trunk encapsulation dot1q
                                      # Set 802.1Q encapsulation
switch(config-if)# switchport mode trunk
                                      # Force interface into trunk mode
switch(config-if)# switchport trunk allowed vlan 10
                                      # Allow VLAN 10 across trunk
switch(config-if)# switchport trunk native vlan 1001
                                      # Set VLAN 1001 as native VLAN

## Layer 3 / Routed Switch Port

switch(config)# int g0/0              # Select interface
switch(config-if)# no switchport      # Convert switchport into Layer 3 interface

## Router-on-a-Stick / Subinterfaces

switch(config)# int g0/0.20           # Create/select subinterface
switch(config-subif)# encapsulation dot1q 20
                                      # Associate subinterface with VLAN 20
switch(config-subif)# ip address 192.168.20.1 255.255.255.0
                                      # Assign Layer 3 address

switch(config-subif)# encapsulation dot1q 20 native
                                      # Make VLAN 20 the native VLAN

## SVI — Switched Virtual Interface

Switch(config)# interface vlan 20
                                      # Create/select SVI for VLAN 20
Switch(config-if)# ip address 192.168.20.1 255.255.255.0
                                      # Assign Layer 3 address to SVI
Switch(config-if)# no shutdown         # Enable SVI

## Port Security

switch(config)# int g0/1              # Select access port
switch(config-if)# switchport mode access
                                      # Port must be in access mode
switch(config-if)# switchport port-security
                                      # Enable port security

switch(config-if)# switchport port-security mac-address FFFF.FFFF.FFFF
                                      # Manually configure secure MAC address

switch(config-if)# switchport port-security mac-address sticky
                                      # Dynamically learn and secure MAC address

