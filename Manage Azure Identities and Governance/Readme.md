# AZ-104 - Microsoft Azure Administrator
## Manage Azure Identity and Governance
### Manage Azure Active Directory (Azure AD) objects
#### Create users and groups

- Create users in Azure Active Directory
- Understand different types of groups
- Create a group and add members
- Manage business-to-business guest accounts

In Azure Active Directory (Azure AD), all the user accounts are granted a set o default permissions. A user's account access consists of the type of user, their role assignments and their ownership of individual objects. <br>

There are different types of user accounts in Azure AD. Each type as a level of access specific to the scope of work expected to be done udner each type of user account. Administrators have the highest level of access, followed by the member user accounts in the Azure AD orgranization. Guests users have the most restricted level of access.

- Permissions and roles <br>
Azure AD uses permissions to help you control the access rights a user or group is granted. This is done trhough roles. Azure AD has many roles with different permissions attached to them. When a user is assigned a specific role, they inherit permissions from that role.

- Administrator roles
Administrator roles in Azure AD allow users elevated access to control who is allowed to do what. You assign these roles to a limited group of users to manage identity tasks in Azure AD organization. You can assign administrator roles that allow a user to create or edit users, assign administative roles to others, reset user passwords, manage user licenses and more. <br>
If a user account has the User Administator or Global Administrator role, you can create a new user in Azure AD by using: <br>
1. Azure portal
2. Azure CLI :  **az ad user crete**
3. PowerShell: **New-AzureADUser**