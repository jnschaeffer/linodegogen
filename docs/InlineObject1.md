# InlineObject1

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**BackupId** | **int32** | A Backup ID from another Linode&#39;s available backups. Your User must have &#x60;read_write&#x60; access to that Linode, the Backup must have a &#x60;status&#x60; of &#x60;successful&#x60;, and the Linode must be deployed to the same &#x60;region&#x60; as the Backup. See [/linode/instances/{linodeId}/backups](/api/v4/linode-instances-linode-id-backups) for a Linode&#39;s available backups.  This field and the &#x60;image&#x60; field are mutually exclusive.  | [optional] 
**BackupsEnabled** | **bool** | If this field is set to &#x60;true&#x60;, the created Linode will automatically be enrolled in the Linode Backup service. This will incur an additional charge. The cost for the Backup service is dependent on the Type of Linode deployed.  This option is always treated as &#x60;true&#x60; if the account-wide &#x60;backups_enabled&#x60; setting is &#x60;true&#x60;.  See [account settings](#operaton/getAccountSettings) for more information.  Backup pricing is included in the response from [/linodes/types](/api/v4/linode-types)  | [optional] 
**SwapSize** | **int32** | When deploying from an Image, this field is optional, otherwise it is ignored. This is used to set the swap disk size for the newly-created Linode.  | [optional] [default to 512]
**Type** | **string** | The [Linode Type](/api/v4/linode-types) of the Linode you are creating.  | 
**Region** | **string** | The [Region](/api/v4/regions) where the Linode will be located.  | 
**Image** | **string** | An Image ID to deploy the Disk from. Official Linode Images start with &#x60;linode/ &#x60;, while your Images start with &#x60;private/&#x60;. See [/images](/api/v4/images) for more information on the Images available for you to use.  | [optional] 
**RootPass** | [**RootPass**](root_pass.md) |  | [optional] 
**AuthorizedKeys** | **[]string** | A list of SSH public keys to deploy for the root user on the newly-created Linode.  Only accepted if &#x60;image&#x60; is provided.  | [optional] 
**StackscriptId** | **int32** | The StackScript to deploy to the newly-created Linode.  If provided, \&quot;image\&quot; must also be provided, and must be an Image that is compatible with this StackScript.  | [optional] 
**StackscriptData** | [**map[string]interface{}**](.md) | An object containing responses to any User Defined Fields present in the StackScript being deployed to this Linode. Only accepted if &#x60;stackscript_id&#x60; is given.  The required values depend on the StackScript being deployed.  | [optional] 
**Booted** | **bool** | Whether to boot this Linode after the deploy is complete. Defaults to true if &#x60;image&#x60; is provided. Not accepted if not deploying from an Image.  | [optional] 
**Label** | [**Label**](label.md) |  | [optional] 
**Tags** | [**Tags**](tags.md) |  | [optional] 
**Group** | [**Group**](group.md) |  | [optional] 
**PrivateIp** | **bool** | If true, the created Linode will have private networking enabled.  | [optional] 
**AuthorizedUsers** | **[]string** | A list of usernames. If the usernames have associated SSH keys, the keys will be appended to the root users &#x60;~/.ssh/authorized_keys&#x60; file automatically.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


