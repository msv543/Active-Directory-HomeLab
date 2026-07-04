# Active Directory Home Lab (Windows Server 2025)

A hands-on Active Directory home lab built with Windows Server 2025 and Windows 11 to simulate a small enterprise enviroment. This repository documents the deployment, configuration, and troubleshooting of common Windows Server roles and Active Directory administration tasks while building practical IT support and system administration skills.

## Lab Environment
### Virtual Machines
```
Machine      Operating System       Role
-------------------------------------------------------------------------------------------------------------------------------
DC1          Windows Server 2025   Domain Controller, DNS, DHCP, Group Policy
FileServer   Windows Server 2025   File Shares, NTFS Permissions, Folder Redirection
PC1          Windows 11            Domain-Joined Client
PC2          Windows 11            Domain-Joined Client
```
## Domain Information
- Domain: martinlab.local
- Directory Services: Active Directory Domain Services (AD DS)
- DNS: Active Directory Integrated DNS
- DHCP: Centralized IP Address Management
- Virtualization Platform: VMware Workstation
----------------------------------------------------------------------------------------------------------------------------
## Completed Labs

1. Domain Setup
2. Users, Groups, and Organizational Units
3. Domain Join
4. DHCP Deployment
5. DNS Configuration
6. Group Policy, Drive Mapping, and File Sharing
7. Delegation of Control (HelpDesk)
8. AppLocker Deployment
9. Microsoft LAPS Deployment
10. Remote Desktop & Windows Firewall
11. Folder Redirection
----------------------------------------------------------------------------------------------------------------------------
## Troubleshooting Labs

This repository also includes a growing collection of troubleshooting scenarios based on real issues encountered while building the lab. Each scenario documents the problem, symptoms, diagnosis, and resolution.

