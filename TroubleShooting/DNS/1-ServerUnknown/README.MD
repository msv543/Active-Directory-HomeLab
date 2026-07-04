# Client Cannot Resolve Domain Names

## Objective

Diagnose and resolve an issue where a domain-joined client could not resolve Active Directory DNS records.

## Symptoms

- Unable to ping martinlab.local
- Domain resources were inaccessible
- nslookup martinlab.local failed
- nslookup displayed Server: Unknown with incorrect server address
- ipconfig /all displayed incorrect DNS server

## Root Cause

The client was configured with an incorrect 'Preferred DNS Server' in its TCP/IPv4 settings. The workstation was not pointing to the Active Directory DNS server (192.168.100.10), it could not resolve internal domain names or locate Active Directory resources.

## Troubleshooting Steps

1. Ran the three following commands on CMD: ping martinlab.local, nslookup martinlab.local, ipconfig /all
2. Verified the output of ping was unable to reach host. Verified the output of nslookup displayed Server: Unknown and incorrect server address. Verified the output of ipconfig/all returned with the incorrect DNS server address.
3. Opened Control Panel
4. Navigated: Network and Internet -> Network and Sharing Center -> Change Adapter Settings -> Ethernet0 -> Properties -> Logged in as Admin Domain -> Internet Protocol Version (TCP/IPv4)
5. Changed the preferred DNS server from 192.168.100.99 to 192.168.100.10 
6. Ran the following command on CMD: ipconfig /flushdns to refresh the client DNS cache
7. Ran the three following commands on CMD: ping martinlab.local, nslookup martinlab.local, ipconfig /all
8. Verified the output of ping returned with 0% packet loss. Verified the output of nslookup returned with the server hostname and correct DNS server address. Verified the output of ipconfig /all returned with the correct DNS server address.

## Resolution

The issue was caused by an incorrect "Preferred DNS Server' in the TCP/IPv4 setting in the client. Changing the DNS to the correct server allowed the client to successfully connect and locate the Active Directory resources.
