## Scope Exhaustion

## Objective

Diagnose and resolve an issue where a domain-joined client can not connect to domain resources or the internet due to scope exhaustion

## Symptoms
- Client recieves an APIPA address (192.168.x.x) 
- ipconfig /renew fails
- Event Viewer shows DHCP-related error
- Existing clients that already have leases continue working until their leases expire

## Root Cause

The DHCP server was configured with an address pool of 192.168.100.100-192.168.100.100. Only PC1 was given the only address and PC2 was given an APIPA address due to exhaustion.

## Troubleshooting Steps

1. On PC2, ran the following two command on CMD:
```
ipconfig /all -> APIPA address given and the DNS Server is correct
ipconfig /renew -> Failed
```
2. On PC1, ran the following command on CMD:
```
ipconfig /all -> IP address was 192.168.100.100 and the DNS Server is correct
```
3. On PC2, Navigated to Event Viewer and found a DHCP-Client error.
4. On Domain Controller 1, Navigated: Server Manager -> DHCP -> dc1.martinlab.local -> IPv4 -> Scope [192.168.100.0] -> Properties
5. The Scope was configured for Start and End IP at 192.168.100.100
6. Changed the Scope to Start IP: 192.168.100.100 and End IP: 192.168.100.200.
7. On PC2, ran the following two commands on CMD:
```
ipconfig release -> Released the current APIPA address
ipconfig /renew -> Receive a new IP from DHCP (192.168.100.132)
```
8. PC2 has Internet access and domain resources are now accessible.
