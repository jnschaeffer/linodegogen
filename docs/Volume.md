# Volume

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The unique ID of this Volume. | [optional] [readonly] 
**Label** | **string** | The Volume&#39;s label is for display purposes only.  | 
**FilesystemPath** | **string** | The full filesystem path for the Volume based on the Volume&#39;s label. Path is /dev/disk/by-id/scsi-0Linode_Volume_ + Volume label.  | [optional] [readonly] 
**Status** | **string** | The current status of the volume.  Can be one of:    * &#x60;creating&#x60; - the Volume is being created and is not yet available     for use.   * &#x60;active&#x60; - the Volume is online and available for use.   * &#x60;resizing&#x60; - the Volume is in the process of upgrading     its current capacity.   * &#x60;contact_support&#x60; - there is a problem with your Volume. Please     [open a Support Ticket](/api/v4/support-tickets/#post) to resolve the issue.  | [optional] [readonly] 
**Size** | **int32** | The Volume&#39;s size, in GiB.  | [optional] 
**Region** | [**Id**](id.md) |  | [optional] 
**LinodeId** | Pointer to **int32** | If a Volume is attached to a specific Linode, the ID of that Linode will be displayed here.  | [optional] 
**LinodeLabel** | Pointer to **string** | If a Volume is attached to a specific Linode, the label of that Linode will be displayed here.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this Volume was created. | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this Volume was last updated. | [optional] [readonly] 
**Tags** | **[]string** | An array of Tags applied to this object.  Tags are for organizational purposes only.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


