# LongviewClient

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Client&#39;s unique ID.  | [optional] [readonly] 
**Label** | **string** | This Client&#39;s unique label. This is for display purposes only.  | [optional] 
**ApiKey** | **string** | The API key for this Client, used when configuring the Longview Client application on your Linode.  | [optional] [readonly] 
**InstallCode** | **string** | The install code for this Client, used when configuring the Longview Client application on your Linode.  | [optional] [readonly] 
**Apps** | [**LongviewClientApps**](LongviewClient_apps.md) |  | [optional] 
**Created** | [**time.Time**](time.Time.md) | When this Longview Client was created.  | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this Longview Client was last updated.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


