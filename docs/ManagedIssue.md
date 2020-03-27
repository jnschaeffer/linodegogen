# ManagedIssue

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Issue&#39;s unique ID.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this Issue was created. Issues are created in response to issues detected with Managed Services, so this is also when the Issue was detected.  | [optional] [readonly] 
**Services** | **[]int32** | An array of Managed Service IDs that were affected by this Issue.  | [optional] [readonly] 
**Entity** | [**ManagedIssueEntity**](ManagedIssue_entity.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


