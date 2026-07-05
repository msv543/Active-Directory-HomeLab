# Missing Reverse Lookup Zone

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve any of the IP -> Hostnames due to a missing Reverse Lookup Zone.

## Symptoms

- nslookup <IP Address> returns non-existent domain
- Applications or logs that rely on reverse DNS may show IP addresses instead of computer names
- DNS Manager has no Reverse Lookup Zones configured

## Root Cause

The Reverse Lookup Zone was deleted or never created, preventing DNS from resolving IP addresses back to hostnames (PTR lookups)

## Troubleshooting Steps

1. Ran the following four commands on CMD:
```
nslookup 192.168.100.10
nslookup dc1.martinlab.local
nslookup 192.168.100.20
nslookup fileserver.martinlab.local
```
2. Verfied that the returns on IP addresses were non-existent domains. The returns on FQDN showed hostname along with the IP address
3. Navigated: Server Manager -> Tools -> DNS -> Reverse Lookup Zones
4. Verified there was a missing Reverse Lookup Zone
5. Recreated the Reverse Lookup Zone (192.168.100.x) and allowed secure dynamic updates
6. Ran the following two commands on administrator level CMD:
```
ipconfig /flushdns
ipconfig /registerdns
```
7. Flushed the DNS to remove incorrect cache and registered the DNS to include all the records
8. Ran nslookup <IP Address> twice and returned successfully with the Hostnames and correct IP addresses.

## Resolution

The issue was caused by a missing Reverse Lookup Zone in the DNS Manager. Recreating the Zone restored the IP -> Hostname resolutions for the domain, allowing clients to successfully use reverse locate and communication.
