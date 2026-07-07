# Group Policy Installments

## Objective

Configure and deploy multiple Group Policy Objects (GPOs) to enforce security standards, manage user enviornments, control device access, map network resources, and automate software deployment within an Active Directory domain.

## Policies Implemented

- Password Policy Enforcement
- Control Panel Restrictinos
- Desktop Wallpaper Configuration
- USB Storage Device Blocking
- Network Drive Mapping
- Google Chrome Software Deployment

## Steps Performed

1. Configured domain-wide password policies:
  - Minimum password length: 10 characters
  - Account lockout threshold: 4 failed logon attempts
2. Created and linked a GPO to restrict access to the Control Panel for users within the Sales and HR Organizational Units (OUs).
3. Configured a desktop wallpaper policy and deployed it to all domain-joined workstations.
4. Implemented a USB storage restriction policy within the Workstations OU to prevent unauthorized removable storage access for Sales and HR users.
5. Created and deployed mapped network drives based on department:
  - Sales Drive
  - HR Drive
  - IT Drive
6. Deployed Google Chrome to all domain workstations using Group Policy Software Installation.

## Results
- Password security requirements successfully enforced across the domain.
- Control Panel access restricted for designated departments.
- Standardized desktop wallpaper applied to all managed workstations.
- USB storage devices blocked according to organizational security requirements.
- Department-specific network drives automatically mapped for users.
- Google Chrome successfully installed on all targeted workstations through Group Policy.
