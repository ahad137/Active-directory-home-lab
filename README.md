# Active-directory-home-lab
A hands-on Windows Active Directory lab focused on domain administration, user and group management, Group Policy, access control, and file-server management.

The lab simulates a small enterprise environment with departmental organizational units, user and group management, security policies, shared resources, mapped drives, and file-management controls.

---

## Lab Environment

| Component | Configuration |
|---|---|
| Domain Controller | Windows Server 2022 |
| Client Machine | Windows 10 Pro |
| Virtualization | Oracle VirtualBox |
| Directory Services | Active Directory Domain Services (AD DS) |
| DNS | Windows DNS |
| Group Management | Active Directory Users and Computers (ADUC) |
| Policy Management | Group Policy Management |
| File Management | File Server Resource Manager (FSRM) |

### Domain

```text
Domain: AHAD.local

Lab Architecture

The lab consists of a Windows Server 2022 Domain Controller and a Windows 10 Pro domain-joined client.

                    Active Directory Domain
                         AHAD.local
                              |
                    Windows Server 2022
                       Domain Controller
                              |
              +---------------+---------------+
              |               |               |
             DNS             AD DS          GPOs
                              |
                    Organizational Units
                              |
              +---------------+---------------+
              |               |               |
           Computers         Users          Groups
                              |
                    +---------+---------+
                    |                   |
              Global Groups       Domain Local Groups
                    |                   |
                    +---------+---------+
                              |
                     Resource Permissions
                              |
                       Shared Resources
                              |
                       Windows 10 Client

Implementation
1. Active Directory Domain Services

Configured Windows Server 2022 as a Domain Controller and established the AHAD.local Active Directory domain.

The environment was configured with Active Directory Domain Services and DNS to provide centralized identity and domain management.

2. Organizational Unit Structure

Created a structured OU hierarchy to organize users, computers, and servers according to their roles and departments.

Example structure:

AHAD.local
│
├── Asia
│   ├── Computers
│   ├── Servers
│   └── Users
│
├── USA
│   ├── Computers
│   ├── Server
│   └── Users
│       ├── HR
│       ├── IT
│       ├── SALES
│       └── Admin
│
└── Group
    ├── Global Group
    └── domain_group

This structure provides a foundation for applying policies and managing resources according to organizational requirements.

3. User Management

Created and organized domain users using Active Directory Users and Computers (ADUC).

Users were organized into departmental OUs such as:

HR
IT
SALES
Admin

This allows users to be managed according to their department and organizational role.

Evidence

4. Security Group Management

Implemented security groups to organize users and manage access to resources.

Global security groups were created for departmental users, including:

GG_ITusers
GG_HRusers
GG_Salesusers

Domain Local groups were also configured for resource-based access management.

The lab used group-based permissions instead of assigning resource permissions individually to every user.

Access Management Model
Users
   ↓
Global Groups
   ↓
Domain Local Groups
   ↓
Resource Permissions

This approach makes access management easier to maintain as the number of users and resources increases.

5. Group Policy Management

Configured multiple Group Policy Objects (GPOs) to centrally manage Windows client configuration and security settings.

Policies implemented
Password Policy
User Rights Assignment
Control Panel restrictions
Desktop configuration
Wallpaper configuration
Drive Mapping
Password Policy

Configured password-related security settings through Group Policy.

User Rights Assignment

Configured user rights through Group Policy to control specific privileges available to users.

Control Panel Policy

Configured restrictions related to Control Panel access.

Desktop Policy

Configured centralized desktop settings using Group Policy.

Wallpaper Policy

Configured centralized wallpaper settings for domain users.

6. Domain-Joined Windows Client

Configured a Windows 10 Pro client and joined it to the AHAD.local domain.

The client was used to verify that domain users, Group Policy settings, authentication, and resource access were functioning as expected.

7. Shared Folders and Permissions

Configured shared resources and practiced managing access through Windows permissions and Active Directory security groups.

The lab was used to understand how users and groups can be assigned access to shared resources without managing permissions individually for every user.

8. Drive Mapping

Configured Group Policy-based drive mapping to automatically provide users with access to network resources.

Drive Mapping Policy

Mapped Drive

Verified that the configured network drive was successfully mapped on the Windows client.

9. File Server Resource Manager

Configured and tested File Server Resource Manager (FSRM) to gain practical experience with Windows file-server management and resource control.

This provided hands-on experience with managing file-server resources in a Windows domain environment.

Skills Demonstrated
Active Directory
Active Directory Domain Services
Active Directory Users and Computers
Organizational Units
Domain users and computers
Security groups
Global Groups
Domain Local Groups
Group-based access management
Windows Administration
Windows Server 2022
Windows 10 Pro
Domain joining
DNS
Windows permissions
Shared resources
Network drive mapping
File Server Resource Manager
Group Policy
Password policies
User Rights Assignment
Control Panel restrictions
Desktop configuration
Wallpaper policies
Drive mapping
Key Learning Outcomes

Through this lab, I gained practical experience with:

Deploying and managing an Active Directory domain
Organizing users and computers using OUs
Managing users and security groups
Implementing group-based resource access
Creating and applying Group Policy
Joining Windows clients to a domain
Managing shared resources and permissions
Configuring network drive mapping
Managing Windows file-server resources
Troubleshooting and verifying domain configurations
Project Purpose

This project was built as a personal hands-on lab to develop practical Windows and Active Directory administration skills.

The environment is designed to simulate common enterprise identity, access-control, policy-management, and Windows administration scenarios.

Future Improvements

Planned improvements include integrating the Active Directory environment with security monitoring tools to collect and analyze Windows security events and develop detection and investigation workflows.

