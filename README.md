# Windows-Server-2022-Lab
This lab simulates a real-world IT environment where I configured a Windows Server domain, managed users and permissions through Active Directory, set up shared folders, handled common user issues, and used key networking tools to troubleshoot and maintain the system.
## 1. Created Virtual Environment Using VirtualBox
I used Oracle VirtualBox to create a virtual lab environment consisting of:
- 1 Windows Server 2022 VM (Domain Controller)
![Server Setup](https://github.com/user-attachments/assets/0d1adb2b-5ab4-4da7-94cb-b5beae0e3a86)
- 2 Windows 10 Client Machines (Desktop 1 and Desktop 2)
![Desktop 1](https://github.com/user-attachments/assets/34851cb1-295e-4f11-9f53-cd61700eb4bc)
![Desktop 2](https://github.com/user-attachments/assets/0997080d-d157-4f23-a3ee-03875b860de5)
---

## 2. Configured Network Adapter (Internal Host-Only)
- Set each VM to use **Adapter 1: Host-only Adapter**
- Ensured all VMs were on the same internal network and could ping each other

---

## 3. Installed and Configured Windows Server 2022
- Mounted Server ISO, set 2048 MB RAM, and created admin credentials
- Installed **Active Directory Domain Services (AD DS)**
- Promoted to Domain Controller  
- Domain: `server.com`

📸 _Insert screenshot of setup here if available_

---

## 4. Set Static IP on Server
- Server IP: `10.1.10.2`
- Clients pointed DNS to server IP  
✅ Enabled smooth domain joining for Windows 10 clients

---![Screenshot 2025-03-25 110730](https://github.com/user-attachments/assets/9bdceb0a-79a5-4d3f-80a0-60230267ee01)


## 5. Setup Client Machines (Windows 10)
- Installed Windows 10 on both clients
- Joined domain `server.com` using server credentials
- Logged in with test domain users

📸 _Insert screenshot of VM settings if available_

---

## DOMAIN SETUP & CONFIGURATION
- Created OUs and users in Active Directory
- Verified domain login vs local login with `.\username`
- Confirmed domain membership using `whoami /fqdn`

---

## IP CONFIGURATION & CMD TOOLS
- `ipconfig /all` – View full IP details  
- `ipconfig /flushdns` – Clear DNS cache  
- `ping <IP>` – Test machine availability

---

## GROUP POLICY (GPO) COMMANDS
- `gpresult /r` – View applied policies  
- `gpupdate /force` – Refresh GPOs  
- Created custom GPOs (e.g., disable Task Manager)

---

## USER MANAGEMENT
- Used `net user <username> /domain` to check:
  - Password expiration
  - Group membership
- Unlocked/reset accounts using Active Directory tools

---

## Shared Folder & Drive Mapping
- Created security groups and shared folders:
  - `\\server\HR`
  - `\\server\%username%` for personal folders
- Applied read/write permissions via AD and GPO

---

## Remote Desktop & Troubleshooting
- Enabled Remote Desktop and Remote Assistance
- Used command line to troubleshoot DNS/login issues
- Remotely accessed registry when needed

---

## Simulated Common User Issues
- Locked/disabled accounts
- Expired passwords
- Domain trust errors (PC rejoin)
- Missing machines (rebuilt and restored)

---

## Key Tools & Technologies
- Active Directory  
- Group Policy Management  
- Remote Desktop  
- Command Line Tools (`ipconfig`, `gpresult`, `net user`)  
- Server Manager  
- VirtualBox  
- Jira  
- MySQL Workbench

---

## Reflection

This project gave me real hands-on experience configuring a domain environment, resolving user issues, and managing IT resources. I improved my troubleshooting skills, got comfortable with Active Directory, and gained confidence using command-line tools and server roles.

---
