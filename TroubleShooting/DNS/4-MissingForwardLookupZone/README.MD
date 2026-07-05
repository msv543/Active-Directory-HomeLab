# Missing Forward Lookup

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve any of the Hostnames due to a missing Forward Lookup Zone.

## Symptoms

- Unable to resolve internal domain names
- nslookup martinlab.local returns with non-existent domain
- Users cannot access shared folders using hostnames
- Network drives mapped by hostname may not reconnect
- Domain logons may fail or take a long time
- Applications that rely on DNS to locate servers stop working

## Root Cause

The DNS Manager was missing a Forward Lookup Zone. Without a Forward Lookup Zone, the DNS server has no records to resolve hostnames within the domain, even though the servers themselves are still online and reachable by IP address.

## Troubleshooting Steps

1. Ran the following four commands on CMD:
```
nslookup martinlab.local
nslookup pc1.martinlab.local
nslookup fileserver.martinlab.local
nslookup pc2.martinlab.local
```
2. The returns for the four commands were: non-existent domain.
3. Navigated: Server Manager -> Tools -> DNS -> DC1 -> Forward Lookup Zones
4. Verified there was a missing Forward Lookup Zone (martinlab.local)
5. Recreated the Forward Lookup Zone (martinlab.local) and allowed secure dynamic updates
6. Ran the following three commands on administrator level CMD:
```
net stop netlogon
net start netlogon
ipconfig /registerdns
```
7. Restarted netlogon service to repopulate the DNS recrods. Registered the server's host (A) name
8. Ran nslookup in CMD on all domains and ping for the FQDN server (dc1.martinlab.local)
9. All returns were successful and client is able to resolve any domain names and connectivity

## Resolution

The issue was caused by a missing Forward Lookup Zone in the DNS Manager. Recreating the Zone restored the hostname resolutions for the domain, allowing clients to successfully locate and communicate.


