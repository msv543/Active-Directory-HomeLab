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

1. 
