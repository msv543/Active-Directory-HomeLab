# Wrong IP Address

## Objective

Diagnose and resolve an issue where a domain-joined client is unable to reach domain resources and has the wrong IP.

## Symptoms

- ipconfig shows wrong/static IP
- Unable to reach domain resources
- ipconfig /renew fails

## Root Cause

The client was configured with an static IP address that was outside of the scope lease under TCP/IP settings. The workstation could not connect to domain resources.

## Troubleshooting Steps

1. Ran the following two commands in CMD:
```
ipconfig /all -> Showed wrong IP address as it is outside the scope range of (!00-200)
ipconfig /renew -> Failed
```
2. Tried to open the Mapped IT Drive under C: and it failed
3. Navigated: Control Panel -> Network and Internet -> Network and Sharing Center -> Change Adapter Settings
4. Static IP address was configured, changed to 'Obtain an IP address automatically.'
5. Ran the following two commands on CMD:
```
ipconfig /release -> Released the current IP
ipconfig /renew -> DHCP gave a new IP (192.168.100.101)
```
6. Access is granted to the IP Mapped Drive and IP given is within our scope range.

## Resolution

The issue was caused by an static IP that was configured in the TCP/IP settings. Changing the setting in the TCP/IP settings to obtain IP addresses automatically and then obtaining a new IP fixed the issue.
