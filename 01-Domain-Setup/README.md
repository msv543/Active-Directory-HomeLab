# Domain Controller Installation

## Objective
Deploy a Windows Server Domain Controller and establish a new Active Directory domain to provide centralized authentication, authorization, and network management services.

## Steps Performed

1. Installed Windows Server 2025.
2. Configured a static IPv4 address to ensure consistent network connectivity.
3. Installed the Active Directory Domain Services (AD DS) role.
4. Promoted the server to a Domain Controller.
5. Created a new Active Directory domain: martinlab.local.
6. Installed and configured DNS as part of the domain deployment process.
7. Verified Active Directory functionality thorugh administrative tools and PowerShell commands.
![01-Domain-Setup](screenshots/6-VerifyingServer.png)

## Results

Successfully deployed a fully functional Domain Controller running Windows 2025. The martinlab.local Active Directory domain was created and configured with integrated DNS services, providing the foundation for centralized user management, Group Policy deployment, authentication services, and future domain-joined workstation administration.
