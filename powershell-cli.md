#PowerShell Command Reference

A structured reference of common PowerShell commands with short explanations.

---

##Navigation & Location

`Get-Location` #show current directory  
`Set-Location` #change directory  
`Get-ChildItem` #list directory contents  
`Get-ChildItem -Force` #list including hidden/system  
`Get-ChildItem "C:\" -Recurse | Unblock-File` #unblock all files recursively  

---

##File & Folder Operations

###Basic File Commands
`Copy-Item` #copy file or folder  
`Move-Item` #move file or folder  
`Remove-Item` #delete file or folder  
`Rename-Item` #rename file or folder

---

##System & Computer Management

`Rename-Computer -NewName "NEO-PC" -Restart` #rename PC and restart  
`Rename-Computer -NewName "NEO-PC" -DomainCredential "DOMAIN\Admin" -Restart` #rename PC in domain  
`Rename-LocalUser -Name "User_" -NewName "Neo"` #rename local user  
`Get-ComputerInfo` #detailed system info  
`Restart-Computer` #restart PC  
`Stop-Computer` #shutdown PC

---

##User & Identity

`Get-LocalUser` #list local users  
`Get-LocalGroup` #list local groups  
`Get-LocalGroupMember Administrators` #list admin group members  
`New-LocalUser -Name "Neo"` #create user  
`Remove-LocalUser -Name "Neo"` #delete user  
`Set-LocalUser -Name "Neo" -Password (Read-Host -AsSecureString)` #set password

---

##Processes & Services

###Processes

`Get-Process` #list processes  
`Stop-Process -Name "notepad"` #kill process  
`Start-Process "notepad.exe"` #start process

---

##Package & Module Management

`Get-Package` #list installed packages  
`Install-Package` #install package  
`Get-Module` #list loaded modules  
`Install-Module` #install module  
`Update-Module` #update module  
`Remove-Module` #unload module


