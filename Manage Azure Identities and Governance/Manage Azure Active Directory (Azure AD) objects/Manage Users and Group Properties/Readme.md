### Build in roles for Azure Resource
Azure AD provides several build-in roles to cover the most common security scenarios
- Owner :   Full access to all resources, including the right to delegate access to others
- Contributor: can crate and manage all types of Azure resources but can't grant access to others
- Reader : Can view existing Azure resources

### Role Definistions:
Each role is a set of properties defined in a JSON. This role definition includes : Name, ID, Description, Actions/NotActions, Scope.

Name	Description <br>
`Id`	Unique identifier for the role, assigned by Azure. <br>
`IsCustom`	True if a custom role, False if a built-in role. <br>
`Description`	A readable description of the role.<br>
`Actions []`	Allowed permissions, * indicates all.<br>
`NotActions []`	Denied permissions.<br>
`DataActions []`	Specific allowed permissions as applied to data, for example `Microsoft.Storage/storageAccounts/blobServices/containers/blobs/read` <br>
`NotDataActions []`	Specific denied permissions as applied to data. ex: `Microsoft.Storage/storageAccounts/blobServices/containers/blobs/delete`<br>
`AssignableScopes []` Scopes where this role applies. / indicates global, but can reach into a hierarchical tree.	`"/subscriptions/{sub-id}"`<br>

Note: </br> 
1. `NotActions` are substracted from `Actions` </br>
2. You specify what actions you want to allow`DataActions` (*) and then provide a list of specific actions to remove in the `NotDataActions`