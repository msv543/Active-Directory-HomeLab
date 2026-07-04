# Missing A Record

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve a domain name

## Symptoms

- Unable to ping fileserver.martinlab.local
- nslookup fileserver returns no record found

## Root Cause

The DNS manager had a missing Host (A) name record for fileserver. The workstations could not resolve that specific domain name but they could ping the actual IP in an reverse lookup.

## Troubleshooting Steps

1. Ran the four following commands on CMD: ping fileserver.martinlab.local, nslookup fileserver, ipconfig /all, ping 192.168.100.20
2. Verified ping fileserver returned with 'non-existent domain.' Verified nslookup fileserver returned 'non-existent domain.' Verified ipconfig /all returned with the correct DNS server. Verified ping server IP worked with 0% packet loss.
3. Opened Server Manager and went through Tools -> DNS -> Forward Lookup Zones -> martinlab.local
4. Verified there was a missing Host (A) record for fileserver
5. Created a new Host (A) record for fileserver with the IP of 192.168.100.20
6. Ran the following two commands on CMD: ping fileserver.martinlab.local, nslookup fileserver
7. Verified ping returned packets at 0% loss. Verified that nslookup returned with the server name and address.

## Resolution

The issue was caused by a missing Host (A) name record. Creating a new Host (A) name record for fileserver allows the clients to successfully resolve the filserver domain.

