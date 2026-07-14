# Linux Command Reference

A structured reference of common Linux commands with sudo equivalents.

---

## System & Identity

`whoami` — show current user  
`whoami -a` — show full identity info  
`hostname` — show system hostname  
`uname -a` — kernel + system info  
`cat /etc/os-release` — Linux distribution info  
`sudo hostnamectl set-hostname neo-linux` — set hostname

---

## Navigation & Location

`pwd` — show current directory  
`cd /path` — change directory  
`ls` — list directory contents  
`ls -la` — list including hidden/system  
`tree` — show folder structure  
`sudo tree /root` — tree with elevated access

---

## File & Directory Operations

### Basic Commands
`cp file.txt /backup/` — copy file  
`mv file.txt /backup/` — move file  
`rm file.txt` — delete file  
`rm -rf folder/` — delete folder recursively  
`mkdir folder` — create folder  
`rmdir folder` — remove empty folder  
`touch file.txt` — create empty file

### Sudo Versions
`sudo cp file.txt /root/` — copy with sudo  
`sudo mv file.txt /root/` — move with sudo  
`sudo rm -rf /root/folder` — delete with sudo  
`sudo mkdir /root/folder` — create folder with sudo

---

## Viewing & Searching

`cat file.txt` — view file  
`less file.txt` — paginated view  
`head file.txt` — first lines  
`tail file.txt` — last lines  
`tail -f /var/log/syslog` — live log view  
`grep "error" file.txt` — search text  
`grep -Ri "error" /var/log/` — recursive search

---

## Permissions & Ownership

`chmod 755 file.sh` — set permissions  
`chmod +x script.sh` — make executable  
`chown neo file.txt` — change owner  
`chown neo:neo file.txt` — change owner + group  
`sudo chown root:root file.txt` — change ownership with sudo

---

## User & Group Management

`id` — show user identity  
`groups` — show group membership  
`sudo adduser neo` — create user  
`sudo deluser neo` — delete user  
`sudo passwd neo` — change password  
`sudo usermod -aG sudo neo` — add user to sudo group  
`sudo groupadd admins` — create group  
`sudo groupdel admins` — delete group

---

## System Management

`top` — live process viewer  
`htop` — enhanced viewer  
`ps aux` — list processes  
`kill 1234` — kill process  
`kill -9 1234` — force kill  
`systemctl status ssh` — service status  
`sudo systemctl restart ssh` — restart service  
`sudo systemctl enable ssh` — enable service  
`sudo systemctl disable ssh` — disable service

---

## Networking

`ip a` — show IP addresses  
`ip r` — show routes  
`ip link` — show interfaces  
`sudo ip link set eth0 up` — enable interface  
`sudo ip link set eth0 down` — disable interface

### Wi‑Fi (Linux equivalents)
`nmcli dev wifi list` — list Wi‑Fi networks  
`nmcli con show` — list saved connections  
`sudo nmcli con delete id "BT-JFAHR7"` — delete Wi‑Fi profile  
`sudo nmcli con add type wifi ifname wlan0 ssid "BT-JFAHR7"` — add Wi‑Fi profile  
`sudo nmcli con up id "BT-JFAHR7"` — connect to Wi‑Fi  
`sudo nmcli dev wifi connect "BT-JFAHR7"` — connect directly

### DNS & IP
`cat /etc/resolv.conf` — show DNS  
`sudo nano /etc/resolv.conf` — edit DNS  
`sudo dhclient -r` — release DHCP  
`sudo dhclient` — renew DHCP  
`ping 8.8.8.8` — test connection  
`traceroute google.com` — trace route  
`dig microsoft.com` — DNS lookup  
`netstat -tulnp` — ports + PIDs

---

## Package Management

### Debian / Ubuntu (APT)
`sudo apt update` — update package list  
`sudo apt upgrade` — upgrade packages  
`sudo apt install htop` — install package  
`sudo apt remove htop` — remove package  
`sudo apt autoremove` — cleanup

### RedHat / CentOS (YUM / DNF)
`sudo dnf install htop` — install  
`sudo dnf remove htop` — remove  
`sudo dnf update` — update packages

### Snap
`snap list` — list snaps  
`sudo snap install code` — install snap  
`sudo snap remove code` — remove snap

---

## Disk & Storage

`df -h` — disk usage  
`du -sh folder/` — folder size  
`lsblk` — block devices  
`mount` — mounted filesystems  
`sudo mount /dev/sdb1 /mnt` — mount drive  
`sudo umount /mnt` — unmount drive  
`sudo fdisk -l` — list partitions  
`sudo mkfs.ext4 /dev/sdb1` — format drive

---

## Archives & Compression

`tar -cvf archive.tar folder/` — create tar  
`tar -xvf archive.tar` — extract tar  
`tar -czvf archive.tar.gz folder/` — create gzip  
`tar -xzvf archive.tar.gz` — extract gzip  
`unzip file.zip` — extract zip  
`zip -r archive.zip folder/` — create zip

---

## System Updates & Upgrades

`sudo apt update && sudo apt upgrade -y` — full update  
`sudo apt dist-upgrade` — major upgrade  
`sudo apt full-upgrade` — kernel + system upgrade  
`sudo reboot` — restart  
`sudo shutdown now` — shutdown

---

## Scripting Essentials

`echo "Hello"` — print text  
`read -p "Enter value: " var` — prompt user  
`var="Neo"` — set variable  
`if [ -f file.txt ]; then echo "Exists"; fi` — condition  
`for i in {1..5}; do echo $i; done` — loop  
`chmod +x script.sh` — make script executable  
`./script.sh` — run script

