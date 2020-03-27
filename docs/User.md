# User

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Username** | **string** | This User&#39;s username. This is used for logging in, and may also be displayed alongside actions the User performs (for example, in Events or public StackScripts).  | [optional] 
**Email** | **string** | The email address for this User, for account management communications, and may be used for other communications as configured.  | [optional] [readonly] 
**Restricted** | **bool** | If true, this User must be granted access to perform actions or access entities on this Account. See [/account/users/{username}/grants](/api/v4/account-users-username-grants) for details on how to configure grants for a restricted User.  | [optional] 
**SshKeys** | **[]string** | A list of SSH Key labels added by this User. These are the keys that will be deployed if this User is included in the &#x60;authorized_users&#x60; field of a [create Linode](/api/v4/linode-instances/#post), [rebuild Linode](/api/v4/linode-instances-linode-id-rebuild/#post), or [create Disk](/api/v4/linode-instances-linode-id-disks/#post) request.  | [optional] 
**TfaEnabled** | **bool** | A boolean value indicating if the User has Two Factor Authentication (TFA) enabled. See the Create Two Factor Secret ([/profile/tfa-enable](/api/v4/profile-tfa-enable/#post)) endpoint to enable TFA.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


