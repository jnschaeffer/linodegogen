# Disk

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Disk&#39;s ID which must be provided for all operations impacting this Disk.  | [optional] [readonly] 
**Label** | **string** | The Disk&#39;s label is for display purposes only.  | [optional] 
**Status** | **string** | A brief description of this Disk&#39;s current state. This field may change without direct action from you, as a result of operations performed to the Disk or the Linode containing the Disk.  | [optional] [readonly] 
**Size** | **int32** | The size of the Disk in MB. | [optional] [readonly] 
**Filesystem** | **string** | The Disk filesystem can be one of:    * raw - No filesystem, just a raw binary stream.   * swap - Linux swap area.   * ext3 - The ext3 journaling filesystem for Linux.   * ext4 - The ext4 journaling filesystem for Linux.   * initrd - initrd (uncompressed initrd, ext2, max 32 MB).  | [optional] 
**Created** | [**time.Time**](time.Time.md) | When this Linode was created. | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this Linode was last updated. | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


