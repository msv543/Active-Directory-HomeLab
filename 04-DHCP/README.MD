# DHCP Installation & Configuration

## Objective

Deploy and configure Dynamic Host Configuration Protocol (DHCP) services to automatically assign IP addressing information to client devices within the network.

## Steps Performed

1. Installed and authorized the DHCP Server role on Windows Server.
![04-DHCP](screenshots/1-DHCPInstalled.png)
2. Configured the default gateway option to use the router's IP address.
3. Configured the DNS server option to use the Domain Controller's IP address.
4. Created and activated a DHCP scope for client devices.
5. Defined an address pool ranging from 192.168.100.100 to 192.168.100.200
![04-DHCP](screenshots/2-DHCPConfigured.png)
6. Verified that client workstation can successfully obtain IP configuration information from the DHCP server.
7. Confirmed network connectivity and proper lease assignment on the client workstation (PC1).
![04-DHCP/screenshots/3-DHCPVerifying.png]

## Results

- Successfully deployed and configured a DHCP server.
- Created and activated a DHCP scope with an address range of 192.168.100.100 - 192.168.100.200.
- Configured DHCP options for default gateway and DNS server distribution.
- Verified successful lease assignment to PC1.
- Confirmed PC1 recieved the IP address 192.168.100.101, which falls within the configured DHCP scope.
- Established automated IP address management for domain-connected devices.
