# Missing Pointer (PTR) Record

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve a reverse DNS Hostname due to a missing Pointer (PTR) record.

## Symptoms

- nslookup 192.168.100.20 returns non-existent domain 
- Reverse DNS lookups fail
- nslookup displays incorrect IP address
- Forward DNS lookups continue to work normally

## Root Cause

The Reverse Lookup Zone was missing the Pointer (PTR) record for the host. Without a PTR record, DNS cannot resolve the IP address back to its corresponding hostname.

## Troubleshooting Steps

1. Ran the following comands on CMD: 
```
nslookup 192.168.100.20
nslookup fileserver
ping 192.168.100.20
```
2. Verified
```
nslookup 192.168.100.20 returned non-existent domain
nslookup fileserver showed correct Hostname and Address
ping 192.168.100.20 succeeded with 0% packet loss, confirming network connectivity
```
3. Navigated: Server Manager -> Tools -> DNS -> DC1.martinlab.local -> Reverse Lookup Zones -> 100.168.192
4. Verified there was no Pointer (PTR) record for 192.168.100.20
5. Recreated the Pointer (PTR) record for 192.168.100.20 -> fileserver.martinlab.local
6. Ran the following command: nslookup fileserver
7. Showed the correct Hostname and address

## Resolution

The issue was caused by a missing Pointer (PTR) record in the DNS Reverse Lookup Zone. Recreating the record restored IP to Hostname resolution, allowing clients to successfully locate and communicate with 192.168.100.20.
