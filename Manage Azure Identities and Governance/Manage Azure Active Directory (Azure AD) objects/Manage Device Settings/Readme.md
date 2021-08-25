# Manage Azure Identities and Governance
## Manage Azure Active Directory (Azure AD)
### Manage Device Settings
- Basics of device identity

Device identity in Azure Active Diretory (Azure AD) helps you control the devices that you and your organization Azure AD instance. It also helps you control the data, resources and assets that those devices can access. It provides a framework to implement device-based conditional access.

- Device registration options
1. Azure AD registered -  These falls into BYOD (Bring Your Own Device) category. They are tipically privately owned or they use a personal Microsoft account or another local account. </br>
It supports : Windows 10, iOS, iPadOS, Android and macOS. </br>
Security: passwords, PIN, pattern or Windows Hello</br>

2. Azure AD join
These devices are owned by your organization. Users access your cloud-based Azure AD instance through their work account. Device identitites exist only in the cloud.
Available: Windows 10, Windows Server 2019
Security: password, Windows Hello

3. Hybrid Azure AD joined
This otpion is similar to Azure AD join. The devices are owned by the organization and they're signed with an Azure AD account that belogns to that organization. Device identities exist in the cloud and on-premises.
Support: Windows 7,8.1,10, Windows Server 2008 or later.

* Conditional access
Conditional access in Azure AD uses data from sources known as signals, validates them agains a user-definable rule base and chooses the best outcome to enforce your organization's security policy. Conditional access policies are applied after a user has successfuly completed first-factor authentication, typically with username and password. They are used to assess factors like: device, location and application and to assess the risk in real time.

####  Signals
- User or group membership - provides fine grained access to resources
- IP location information - uses an allow list of trusted IP addresses, and a deny list of blocked / banned IP Addresses.
- Device -  Allows you to control access to an application from a specific device
- Real time and calculated risk detection - allows Azure AD to identify behaviours not only during sing-in but also throughout the users's session
- Microsoft Cloud App Security -  provides real-time monitoring of the users's sessions and application access. 

### Common Decisions
- Block Access = most restrictive
- Grant Access = the least restrictive, BUT might require additioal criteria:
    * Multifactor authentication
    * Device marked as compliant
    * Device that hybrid Azure AD join
    * Approved application
    * Need for an app protection polity

#### Benefits of Device Identity
- The combination simplifies the procedure for adding and managing devies in Azure AD
- The combination reduces the frcition for users when they;re switching between devies
- Azure AD supports MDM tools such as Microsoft Intune
- You can use single Sign-On (SSO) with any registered or joind devices