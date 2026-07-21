# Windows NETSH & Network CMD Reference

A focused reference for Wi‑Fi, network interfaces, IP configuration, DNS, and reset commands.

---

## Wi‑Fi Profiles & Networks

`netsh wlan show profiles` — list saved Wi‑Fi profiles  
`netsh wlan show network` — list visible Wi‑Fi networks  
`netsh wlan show profile name=Wi-Fi key=clear` — show Wi‑Fi password  
`netsh wlan delete profile name=BT-JFAHR7` — delete Wi‑Fi profile  
`netsh wlan add profile filename="C:\WiFiProfiles\BT-JFAHR7.xml"` — import Wi‑Fi profile  
`netsh wlan connect name=BT-JFAHR7` — connect to Wi‑Fi

---

## Network Interfaces

`netsh int show int` — show network interfaces  
`netsh int set int Wi-Fi Disable` — disable Wi‑Fi  
`netsh int set int Wi-Fi Enable` — enable Wi‑Fi

---

## Static IP Configuration

`netsh interface ipv4 set address name="Wi-Fi" static 192.168.1.77 255.255.255.0 192.168.1.254` — set static IP for Wi‑Fi  
`netsh interface ipv4 set address name="Ethernet0" static 192.168.1.77 255.255.255.0 192.168.1.254` — set static IP for Ethernet

---

## DHCP Configuration

`netsh interface ipv4 set address name="Wi-Fi" source=dhcp` — set Wi‑Fi to DHCP  
`netsh interface ipv4 set dns name="Wi-Fi" source=dhcp` — set DNS to DHCP

---

## Network Reset Commands

`netsh winsock reset` — reset Winsock catalog  
`netsh int ip reset` — reset TCP/IP stack

