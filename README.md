# Windows-Server-2022-Lab
**Date Started:** October 23, 2024

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
![Network Config](https://github.com/user-attachments/assets/e79c62dd-48f7-487f-9bcc-5b56eb2cb800)
---

## 3. Installed and Configured Windows Server 2022
- Mounted Server ISO, set 2048 MB RAM, and created admin credentials
- Installed **Active Directory Domain Services (AD DS)**
- Promoted to Domain Controller  
- Domain: `server.com`
![Domain settings](https://github.com/user-attachments/assets/8b769247-b083-4a19-9b23-6bb1206d76c7)
![Server Manager](https://github.com/user-attachments/assets/17f84d83-b289-4d79-889f-400f75aada15)

---

## 4. Set Static IP on Server
- Server IP: `10.1.10.2`
- Clients pointed DNS to server IP  
- Enabled smooth domain joining for Windows 10 clients


## 5. Setup Client Machines (Windows 10)
- Installed Windows 10 on both clients  
- Joined domain `server.com` using server credentials  
- Logged in with test domain users  

I created and assigned two test users to simulate real-world departments:

- **Patty** – added to the `HR` Organizational Unit (OU)
![Patty](https://github.com/user-attachments/assets/b81ae472-7574-47f3-b9db-41c7e9b8ae2a)
- **Helpdesk** – added to the `IT` Organizational Unit (OU) with elevated permissions (member of Admin and Domain Admin groups)
![Helpdesk](https://github.com/user-attachments/assets/3bd6e10b-49ba-4dba-a759-dbdd3a87caf0)

---

## DOMAIN SETUP & CONFIGURATION
- Created Organizational Units (OUs) and users in Active Directory
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
- `gpresult /h gpreport.html` - Export group policy report to view in browser
- `gpupdate /force` – Refresh GPOs  
- Created custom GPOs (e.g., disable Task Manager)
![gpreport1](https://github.com/user-attachments/assets/5daaf62a-7a9d-4373-a3a1-aaf523d53d6d)
![gpreport2](https://github.com/user-attachments/assets/36c7504c-6505-4661-9816-f5229121c370)

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
![Sharedfolder](https://github.com/user-attachments/assets/943e258e-9f3a-433e-9b75-33d6a4354258)

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

---

## Reflection

This project gave me real hands-on experience configuring a domain environment, resolving user issues, and managing IT resources. I improved my troubleshooting skills, got comfortable with Active Directory, and gained confidence using command-line tools and server roles.

---
