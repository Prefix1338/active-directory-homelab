# Active Directory Homelab

Built a Windows Server 2022 Active Directory lab in VirtualBox to simulate a small enterprise environment with departmental users, security groups, file shares, Group Policy, wallpaper deployment, and network drive mapping.

## Project Overview

This lab simulates a company environment with three departments:

- HR
- IT
- Sales

The environment includes:

- Windows Server 2022 domain controller
- Domain-joined Windows client
- Organizational Units (OUs)
- Department users and security groups
- Shared folders with NTFS + share permissions
- Group Policy Objects (GPOs)
- Wallpaper deployment by department
- Network drive mapping with item-level targeting

## Environment

- Oracle VirtualBox
- Windows Server 2022
- Windows client VM
- Active Directory Domain Services (AD DS)
- Group Policy Management
- SMB file shares

## What I Configured

### Active Directory
- Created a domain environment
- Joined a client PC to the domain
- Created departmental OUs:
  - HR
  - IT
  - Sales

### Users and Groups
- Created department users
- Created security groups:
  - HR_Group
  - IT_Group
  - Sales_Group
- Added users to the correct security groups

### Shared Folders and Permissions
- Created department shares:
  - HR_Files
  - IT_Files
  - Sales_Files
- Configured both:
  - Share permissions
  - NTFS permissions
- Applied role-based access using security groups

### Group Policy
- Applied department-based wallpaper via GPO
- Configured drive mapping using Group Policy Preferences
- Used item-level targeting so drives map only for the correct security group

### Drive Mapping
- HR users receive:
  - H: -> \\192.168.1.10\HR_Files
- IT users receive:
  - I: -> \\192.168.1.10\IT_Files
- Sales users receive:
  - S: -> \\192.168.1.10\Sales_Files

## Troubleshooting Performed

During the lab, I diagnosed and fixed several real-world issues, including:

- Domain join failures caused by DNS/network configuration
- GPO settings not applying as expected
- Share name vs folder name mismatches
- NTFS permissions vs share permissions conflicts
- User not receiving mapped drive because group membership or GPO link was incorrect
- Access denied issues caused by missing permissions
- Shutdown/logoff issues caused by policy and user-rights assignment conflicts

## Key Skills Demonstrated

- Active Directory administration
- Windows Server administration
- Group Policy configuration
- Group Policy Preferences
- SMB share configuration
- NTFS and share permissions
- Security group-based access control
- Drive mapping
- Troubleshooting domain and GPO issues

## Screenshots

### Active Directory Structure
- AD-users-and-groups.png  
- AD-users-and-groups1.png  
- AD-users-and-groups2.png  

### Drive Mapping Configuration
- drive-mapping.png  

### GPO Configuration
- HR-GPO-wallpapers.png  

### Client-Side Drive Mapping
- HR-drive-mapping(user-side view).png  
- IT-drive-mapping(user-side view).png  
- Sales-drive-mapping(user-side view).png  

### Share Permissions
- share-permissions1.png  
- share-permissions2.png  

## What I Learned

This project improved my understanding of:
- OU vs security group design
- Why permissions should be assigned to groups instead of individual users
- Difference between share permissions and NTFS permissions
- How GPO scope, linking, and targeting affect deployment
- How to troubleshoot common enterprise Windows administration problems
