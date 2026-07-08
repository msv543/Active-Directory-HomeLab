# DNS Administration

## Objective

Configure and manage DNS services in an Active Directory environment to support hostname resolution, reverse lookups, Active Directory functionality, and client connectivity.

## Steps Performed

1. Opened DNS Manager on the Domain Controller and reviewed the Active Directory-intergrated Forward Lookup Zone.
2. Examined existing DNS records including A, NS, SOA, and SRV records using Active Directory.
3. Created DNS Host (A) records for FILESERVER, PRINTSERVER, and APPSERVER.
4. Verified hostname resolution from Windows 11 client using nslookup.
5. Created a Reverse Lookup Zone for the lab network.
![05-DNS](screenshots/1-DNSCreation.png)
6. Verified reverse DNS resolution by testing IP-to-hostname lookups using nslookup.
7. Configured DNS Forwarders to allow external name resolution.
8. Test internet hostname resolution through the DNS server.
9. Verified successful Dynamic DNS registration within the DNS zone.
10. Created a CNAME (Alias) record to provide an alternate hostname for a network resource.
[05-DNS](screenshots/2-DNSVerify.png)

## Results

- Successfully configured and adminstered DNS within an Active Directory environment.
- Created and validated Host (A), PTR, and CNAME records.
- Verified both forward and reverse DNS resolutions.
- Confirmed Dynamic DNS registration for domain-joined clients.
- Verified proper DNS functionality to support Active Directory authentication and network resource access.
