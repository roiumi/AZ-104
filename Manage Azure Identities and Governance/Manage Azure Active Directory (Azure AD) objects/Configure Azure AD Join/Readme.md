# Manage Azure Identities and Governance
## Manage Azure Active Directory (Azure AD)
### Configure Azure AD join

- With Azure AD join you can join devices to your Azure Active Directory organization without needing to sync with an on-premises Active Directory instance. Azure AD join is best suited to organizations that are principally cloud based, although it can operate in a hybrid cloud an on-premises environment
- Supported Devices
Windows 10, Widows Server 2019. (NO Windows Server 2019 Server CORE)

###  Identify Infrastructure
- Managed environment -  This environment uses pass-through authentication or password hash sync to provide SSO to your devices
- Federated environments - These environments require the use of an identity provider that must support WS-Trust and WS-Fed protocols with Azure AD join to work natively with Windows devices.
- Smart card and certificate-nbased authentication : These methods aren't valid to join devices to Azure AD, but with Active Directory Federation Services configured, you can use smart cards to sign in to Azure AD joined devices.
- Manual user configuration - If you careate users in you on-premises Active Directory instance, you need to syncronize the account to Azure AD by usign Azure AD connect.

MDM - Mobile Device Managmenet
 Azure AD join uses the mobile device management platform to manage devices attached to Azure AD. MDM provides a means to enforce organization-requirement configuration like: requiring storage to be encrypted, password complexity, software installation, software updates.

 To manage Azure AD join devices there are two approaches:
 1. MDM only: 
 All joined devies are managed exclusevly trough MDM provider (line INTUNE)
 2. Co-Management:
 All joined devies use a combination of a lically installed System Center Configuratio Management agent and your MDM provider. Microsoft INTUNE provides co-manangement capabilities through Configuration Manager.

 ### Considerations for resources and application access
 - recommendation to move all applications and resources in azure
 1. Cloud-Based Applications :  Any migrated apps and all new applications will be added to the Azure AD app gallery. Users with SSO can access them.
 2. On-Premises web applications :  any bespoke or custom-made software that is hosted on-premises can still be accessed through Azure AD join. Access to those applications needs each user to add the app to their trusted sites or intranet zone.
 3. Other devices : This option include existing applications through earlier protocols and on-premises network shares
 4. Printer resources : These resource won't automatically be available through Azure AD join. Users still can connect to a printer directly, by using its UNC path.

 ##### Provisioning options
 1. Self-service: Requires users to manually configure the device during Windows OOBE (Out of Box Experience) for new devices, or by using Windows settings. This is for users with strong technical background.
 2. Windows Autopilot -  Allows you to preconfigure Windows devices, including automatically joining the device to the Active Directory oraniation, Automatic MDM enrollment anc creating cutom OOBE content. This simplifies the management and deployment ofdevices accross the organization.
 3. Bulk enrollment -  Let you set up a provisioning package that applies to a large number of new Windows devices at the same time.

 