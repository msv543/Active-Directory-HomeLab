# Microsoft LAPS Deployment & Configuration

## Objective

Deploy and configure Microsoft LAPS (Local Adminstrator Password Solution) to automatically manage and secure local adminstrator passwords on domain-joined computers through Active Directory.

## Steps Performed
1. Extended the Active Directory schema to support Microsoft LAPS attributes.
2. Created a dedicated Workstations OU and moved domain-joined client computers into the OU.
3. Granted computer accounts permission to update their own LAPS password information in Active Directory.
4. Cerated a security group named LAPS-Admins for delegated password management.
5. Created and linked a Group Policy Object (GPO) to the workstations OU.
6. Configured Microsoft LAPS settings to back up local adminstrator passwords to Active Directory.
7. Configured password complexity, password length, and password expiration policies.
8. Applied Group Policy updates to the client workstation.
9. Verified that password informatino was successfully stored within Active Directory.
10. Tested password retrieval using an authorized administrative account.
11. Verified that unauthorized users could not access managed passwords.

## Results

- Successfully deployed Microsoft LAPS within the Active Directory environment.
- Extended the Active Directory schema to support LAPS password storage.
- Configured automatic local adminstrator password managemnt for domain-joined workstations.
- Implemented password backup to Active Directory.
- Established delegated access through the LAPS-Admins security group.
- Verified successful password retrieval by authorized administrators.
- Confirmed that unauthorized accounts were unable to view managed passwords.
- Improved endpoint security by replacing shared local adminstrator credentials with unique, centrally managed passwords.
- Demonstrated Active Directory adminstration, Group Policy management, security delegation, and least-privilege access control principles.
