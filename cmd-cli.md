# Windows CMD Reference

A clean, structured reference of common Windows CMD commands with short explanations.

---

## System Information

`systeminfo` — OS + hardware details  
`driverquery` — list installed drivers  
`wmic os get caption` — OS edition  
`wmic cpu get name` — CPU model  
`wmic bios get serialnumber` — BIOS serial  
`winver` — Windows version GUI  
`ver` — Windows version console  
`powercfg /batteryreport` — generate battery report  
`powercfg /energy` — generate energy diagnostics

---

## User & Identity

`whoami` — current user  
`whoami /all` — full security token details  
`hostname` — computer name  
`echo %username%` — username  
`net user` — list users  
`net user Neo` — user details  
`net accounts` — password policy  
`whoami /groups` — security groups

---

## Group Management

`net localgroup` — list groups  
`net localgroup administrators TestUser123 /add` — add user to admins  
`net user TestUser123 P@ssw0rd123 /add` — create user  
`net user TestUser123 /delete` — delete user

---

## Network & Connectivity

### IP & DNS
`ipconfig` — IP config  
`ipconfig /all` — full details  
`ipconfig /flushdns` — clear DNS cache  
`ipconfig /release` — drop IP  
`ipconfig /renew` — renew IP

### Connectivity Tools
`ping -t 8.8.8.8` — test connection  
`tracert google.com` — trace route  
`nslookup microsoft.com` — DNS lookup

### Ports & Wi‑Fi
`netstat -ano` — ports + PIDs  
`netsh wlan show profiles` — Wi‑Fi profiles  
`netsh wlan show profile name=Home key=clear` — Wi‑Fi password

### Network Drives
`net use Z: \\Matrix\Agent` — map drive  
`net use Z: /delete` — unmap drive

---

## Environment Variables

`set` — list all variables  
`set PATH=%PATH%;C:\Tools` — append PATH  
`echo %path%` — show PATH  
`echo %cd%` — current directory  
`echo %userprofile%` — profile path

---

## Console & Display

`cls` — clear screen  
`color A` — change console text color  
`title MyCMD` — set window title  
`mode con: cols=120 lines=40` — resize console

---

## Navigation

`cd C:\Users\user_Neo` — change directory  
`cd ..` — go up one level  
`dir` — list directory  
`dir /s` — recursive listing  
`dir /a` — show hidden/system files  
`tree` — folder 

---

## Files & Directories

### Folder Operations
`mkdir TestFolder` — create folder  
`rmdir TestFolder` — remove folder  
`rmdir /s /q Folder` — remove folder recursively

### File Operations
`copy file.txt D:\Backup\` — copy file  
`xcopy C:\Data D:\Backup /E` — copy directory  
`robocopy C:\Data D:\Backup /MIR` — mirror directory  
`move file.txt D:\` — move file  
`del file.txt` — delete file  
`del /f /q *.log` — force delete logs

### Search
`where /r C:\ *Oracle*` — recursive search  
`find "Neo" Matrix.txt` — search text  
`findstr /s /i "error" *.log` — search logs

### Viewing
`type Matrix.txt` — show file  
`more Matrix.txt` — paginated view  
`start "" "Matrix.mp4"` — open file  
`curl ascii.live/Rick` — ASCII animation

---

## Disk & Storage

`diskpart` — disk partition tool  
`chkdsk C:` — check disk  
`format D:` — format drive  
`label C: SYSTEM` — rename volume  
`fsutil fsinfo drives` — list drives  
`fsutil file createnew test.bin 1000` — create file of size  
`wmic logicaldisk get name,freespace,size` — disk info

---

## Processes & Services

### Processes
`tasklist` — list processes  
`tasklist /svc` — processes + services  
`taskkill /im notepad.exe /f` — kill by name  
`taskkill /pid 1234 /f` — kill by PID  
`wmic process list brief` — quick process list  
`wmic process where name="chrome.exe" delete` — kill via WMIC

### Services
`wmic service list brief` — list services  
`sc query` — service status  
`sc stop spooler` — stop service  
`sc start spooler` — start service

---

## File Attributes

`attrib +h +s +r Neo` — hide, system, read‑only  
`attrib -h -s -r /s /d *.*` — remove attributes  
`attrib +a file.txt` — archive flag  
`attrib -a file.txt` — remove archive flag

---

## Security & Permissions

`cacls file.txt` — view permissions  
`icacls file.txt` — advanced permissions  
`icacls file.txt /grant Neo:F` — full access  
`icacls file.txt /inheritance:r` — remove inheritance  
`cipher /w:C:` — wipe free space  
`cipher /e file.txt` — encrypt  
`cipher /d file.txt` — decrypt

---

## Power & Shutdown

`shutdown /a` — abort shutdown  
`shutdown /s /t 0` — shutdown  
`shutdown /r /t 0` — reboot  
`shutdown /l` — log off  
`shutdown /h` — hibernate
`logoff` — sign out

---

## System Utilities

`control` — Control Panel  
`compmgmt.msc` — Computer Management  
`services.msc` — Services  
`eventvwr` — Event Viewer  
`taskmgr` — Task Manager  
`regedit` — Registry Editor  
`msinfo32` — System Info  
`dxdiag` — DirectX diagnostic  
`cleanmgr` — Disk Cleanup  
`sysdm.cpl` — System Properties  
`ncpa.cpl` — Network Connections  
`appwiz.cpl` — Programs & Features

---

## Group Policy & Active Directory

### Group Policy
`gpresult /r` — applied GPOs  
`gpupdate /force` — refresh GPOs  
`gpupdate /target:computer /force` — refresh computer  
`gpupdate /target:user /force` — refresh user

### Active Directory
`repadmin /replsummary` — replication summary  
`repadmin /showrepl` — replication partners  
`repadmin /syncall /PedA` — sync all DCs  
`repadmin /queue` — replication queue  
`nltest /dsgetdc:domain.local` — find DC  
`nltest /dclist:domain.local` — list DCs  
`dcdiag` — DC diagnostics

---

## Boot & Recovery

`bcdedit` — boot config  
`bootrec /fixmbr` — repair MBR  
`bootrec /fixboot` — repair boot sector  
`bootrec /scanos` — scan OS installs  
`bootrec /rebuildbcd` — rebuild boot config  
`sfc /scannow` — repair system files  
`DISM /Online /Cleanup-Image /RestoreHealth` — repair Windows image
