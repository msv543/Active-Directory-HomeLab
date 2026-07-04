# Missing A Record

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve a host name due to a missing DNS Host (A) record.

## Symptoms

- Unable to ping fileserver.martinlab.local
- nslookup fileserver returned non-existent domain
- The server was reachable by IP address and not by hostname

## Root Cause

The DNS Forward Lookup Zone was missing the Host (A) record for fileserver because no A record existed, clients could not resolve the hostname to its IP address. Network connectivity remaind functional, allowing the server to be reached directly by its IP address.

## Troubleshooting Steps

1. Ran the four following commands on CMD
```
ping fileserver.martinlab.local
nslookup fileserver
ipconfig /all
ping 192.168.100.20
```
2. Verified ping fileserver returned with 'non-existent domain.' Verified nslookup fileserver returned 'non-existent domain.' Verified ipconfig /all returned with the correct DNS server. Verified ping server IP worked with 0% packet loss.
3. Opened Server Manager and went through Tools -> DNS -> Forward Lookup Zones -> martinlab.local
4. Verified there was a missing Host (A) record for fileserver
5. Created a new Host (A) record for fileserver with the IP of 192.168.100.20
6. Ran the following two commands on CMD: ping fileserver.martinlab.local, nslookup fileserver
7. Verified ping returned packets at 0% loss. Verified that nslookup returned with the server name and address.

## Resolution

The issue was caused by a missing Host (A) name record. Creating a new Host (A) name record for fileserver allows the clients to successfully resolve the filserver domain.

