# PowerShell Command Reference

A structured reference of common PowerShell commands with short explanations.

---

## Navigation & Location

`Get-Location` — show current directory  
`Set-Location` — change directory  
`Get-ChildItem` — list directory contents  
`Get-ChildItem -Force` — list including hidden/system  
`Get-ChildItem "C:\" -Recurse | Unblock-File` — unblock all files recursively  
`ls` — alias for `Get-ChildItem`  
`dir` — alias for `Get-ChildItem`  
`cd` — alias for `Set-Location`

---

## File & Folder Operations

### Basic File Commands
`Copy-Item` — copy file or folder  
`Move-Item` — move file or folder  
`Remove-Item` — delete file or folder  
`Rename-Item` — rename file or folder

### Examples
`Move-Item -Path "C:\Temp\Folder1" -Destination "D:\Backup\" -Force` — move folder  
`Copy-Item "C:\Data\file.txt" "D:\Backup\"` — copy file  
`Remove-Item "C:\Temp\*.log" -Force` — delete logs  
`Rename-Item "old.txt" "new.txt"` — rename file

---

## System & Computer Management

`Rename-Computer -NewName "NEO-PC" -Restart` — rename PC and restart  
`Rename-Computer -NewName "NEO-PC" -DomainCredential "DOMAIN\Admin" -Restart` — rename PC in domain  
`Rename-LocalUser -Name "User_" -NewName "Neo"` — rename local user  
`Get-ComputerInfo` — detailed system info  
`Restart-Computer` — restart PC  
`Stop-Computer` — shutdown PC

---

## User & Identity

`Get-LocalUser` — list local users  
`Get-LocalGroup` — list local groups  
`Get-LocalGroupMember Administrators` — list admin group members  
`New-LocalUser -Name "Neo"` — create user  
`Remove-LocalUser -Name "Neo"` — delete user  
`Set-LocalUser -Name "Neo" -Password (Read-Host -AsSecureString)` — set password

---

## Network & IP Configuration

### Network Interfaces
`Get-NetAdapter` — list network adapters  
`Enable-NetAdapter -Name "Wi-Fi"` — enable Wi‑Fi  
`Disable-NetAdapter -Name "Wi-Fi"` — disable Wi‑Fi  
`Restart-NetAdapter -Name "Wi-Fi"` — restart adapter

### IP Addressing
`Get-NetIPAddress` — show IP addresses  
`New-NetIPAddress -InterfaceAlias "Wi-Fi" -IPAddress 192.168.1.77 -PrefixLength 24 -DefaultGateway 192.168.1.254` — set static IP  
`Set-DnsClientServerAddress -InterfaceAlias "Wi-Fi" -ServerAddresses 8.8.8.8` — set DNS  
`Set-DnsClientServerAddress -InterfaceAlias "Wi-Fi" -ResetServerAddresses` — reset DNS to DHCP  
`Remove-NetIPAddress -InterfaceAlias "Wi-Fi"` — remove IP config

### Wi‑Fi (PowerShell equivalents)
`netsh wlan show profiles` — list saved Wi‑Fi profiles  
`netsh wlan show network` — list visible networks  
`netsh wlan show profile name=Wi-Fi key=clear` — show Wi‑Fi password  
`netsh wlan delete profile name=BT-JFAHR7` — delete profile  
`netsh wlan add profile filename="C:\WiFiProfiles\BT-JFAHR7.xml"` — import profile  
`netsh wlan connect name=BT-JFAHR7` — connect to Wi‑Fi

---

## Processes & Services

### Processes
`Get-Process` — list processes  
`Stop-Process -Name "notepad"` — kill process  
`Start-Process "notepad.exe"` — start process

### Services
`Get-Service` — list services  
`Start-Service -Name "Spooler"` — start service  
`Stop-Service -Name "Spooler"` — stop service  
`Restart-Service -Name "Spooler"` — restart service

---

## Security & Permissions

`Get-Acl "C:\File.txt"` — view permissions  
`Set-Acl "C:\File.txt" $acl` — apply permissions  
`Unblock-File "C:\Downloads\script.ps1"` — unblock downloaded file  
`Get-AuthenticodeSignature "script.ps1"` — check script signature

---

## System Utilities

`Get-EventLog -LogName System -Newest 50` — recent system events  
`Get-WmiObject Win32_ComputerSystem` — system info  
`Get-WmiObject Win32_LogicalDisk` — disk info  
`Get-WmiObject Win32_BIOS` — BIOS info  
`Get-WmiObject Win32_NetworkAdapterConfiguration` — network config

---

## Package & Module Management

`Get-Package` — list installed packages  
`Install-Package` — install package  
`Get-Module` — list loaded modules  
`Install-Module` — install module  
`Update-Module` — update module  
`Remove-Module` — unload module

---

## PowerShell Execution Policy

`Get-ExecutionPolicy` — show policy  
`Set-ExecutionPolicy RemoteSigned` — allow local scripts  
`Set-ExecutionPolicy Unrestricted` — allow all scripts  
`Set-ExecutionPolicy Restricted` — block scripts

---

## Scripting Essentials

`Write-Output "Hello"` — print text  
`Read-Host "Enter value"` — prompt user  
`$var = "Neo"` — set variable  
`if ($true) { Write-Output "OK" }` — basic condition  
`foreach ($i in 1..5) { Write-Output $i }` — loop  
`Get-Help Get-ChildItem -Full` — full help  
`Get-Command` — list all commands

