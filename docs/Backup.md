# Backup

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The unique ID of this Backup. | [optional] [readonly] 
**Type** | **string** | This indicates whether the Backup is an automatic Backup or manual snapshot taken by the User at a specific point in time.  | [optional] [readonly] 
**Status** | **string** | The current state of a specific Backup. | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | The date the Backup was taken. | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | The date the Backup was most recently updated. | [optional] [readonly] 
**Finished** | [**time.Time**](time.Time.md) | The date the Backup completed. | [optional] [readonly] 
**Label** | Pointer to **string** | A label for Backups that are of type &#x60;snapshot&#x60;. | [optional] 
**Configs** | **[]string** | A list of the labels of the Configuration profiles that are part of the Backup.  | [optional] [readonly] 
**Disks** | [**[]BackupDisks**](Backup_disks.md) | A list of the disks that are part of the Backup.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


