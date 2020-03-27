# ManagedContact

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Contact&#39;s unique ID.  | [optional] [readonly] 
**Name** | **string** | The name of this Contact.  | [optional] 
**Email** | **string** | The address to email this Contact to alert them of issues.  | [optional] 
**Phone** | [**ManagedContactPhone**](ManagedContact_phone.md) |  | [optional] 
**Group** | Pointer to **string** | A grouping for this Contact. This is for display purposes only.  | [optional] 
**Updated** | [**time.Time**](time.Time.md) | When this Contact was last updated.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


