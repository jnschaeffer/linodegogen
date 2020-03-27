# \LinodeInstancesApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**AddLinodeConfig**](LinodeInstancesApi.md#AddLinodeConfig) | **Post** /linode/instances/{linodeId}/configs | Create Configuration Profile
[**AddLinodeDisk**](LinodeInstancesApi.md#AddLinodeDisk) | **Post** /linode/instances/{linodeId}/disks | Create Disk
[**AddLinodeIP**](LinodeInstancesApi.md#AddLinodeIP) | **Post** /linode/instances/{linodeId}/ips | Allocate IPv4 Address
[**BootLinodeInstance**](LinodeInstancesApi.md#BootLinodeInstance) | **Post** /linode/instances/{linodeId}/boot | Boot Linode
[**CancelBackups**](LinodeInstancesApi.md#CancelBackups) | **Post** /linode/instances/{linodeId}/backups/cancel | Cancel Backups
[**CloneLinodeDisk**](LinodeInstancesApi.md#CloneLinodeDisk) | **Post** /linode/instances/{linodeId}/disks/{diskId}/clone | Clone Disk
[**CloneLinodeInstance**](LinodeInstancesApi.md#CloneLinodeInstance) | **Post** /linode/instances/{linodeId}/clone | Clone Linode
[**CreateLinodeInstance**](LinodeInstancesApi.md#CreateLinodeInstance) | **Post** /linode/instances | Create Linode
[**CreateSnapshot**](LinodeInstancesApi.md#CreateSnapshot) | **Post** /linode/instances/{linodeId}/backups | Create Snapshot
[**DeleteDisk**](LinodeInstancesApi.md#DeleteDisk) | **Delete** /linode/instances/{linodeId}/disks/{diskId} | Delete Disk
[**DeleteLinodeConfig**](LinodeInstancesApi.md#DeleteLinodeConfig) | **Delete** /linode/instances/{linodeId}/configs/{configId} | Delete Configuration Profile
[**DeleteLinodeInstance**](LinodeInstancesApi.md#DeleteLinodeInstance) | **Delete** /linode/instances/{linodeId} | Delete Linode
[**EnableBackups**](LinodeInstancesApi.md#EnableBackups) | **Post** /linode/instances/{linodeId}/backups/enable | Enable Backups
[**GetBackup**](LinodeInstancesApi.md#GetBackup) | **Get** /linode/instances/{linodeId}/backups/{backupId} | View Backup
[**GetBackups**](LinodeInstancesApi.md#GetBackups) | **Get** /linode/instances/{linodeId}/backups | List Backups
[**GetKernel**](LinodeInstancesApi.md#GetKernel) | **Get** /linode/kernels/{kernelId} | View Kernel
[**GetKernels**](LinodeInstancesApi.md#GetKernels) | **Get** /linode/kernels | List Kernels
[**GetLinodeConfig**](LinodeInstancesApi.md#GetLinodeConfig) | **Get** /linode/instances/{linodeId}/configs/{configId} | View Configuration Profile
[**GetLinodeConfigs**](LinodeInstancesApi.md#GetLinodeConfigs) | **Get** /linode/instances/{linodeId}/configs | List Configuration Profiles
[**GetLinodeDisk**](LinodeInstancesApi.md#GetLinodeDisk) | **Get** /linode/instances/{linodeId}/disks/{diskId} | View Disk
[**GetLinodeDisks**](LinodeInstancesApi.md#GetLinodeDisks) | **Get** /linode/instances/{linodeId}/disks | List Disks
[**GetLinodeIP**](LinodeInstancesApi.md#GetLinodeIP) | **Get** /linode/instances/{linodeId}/ips/{address} | View IP Address
[**GetLinodeIPs**](LinodeInstancesApi.md#GetLinodeIPs) | **Get** /linode/instances/{linodeId}/ips | List Networking Information
[**GetLinodeInstance**](LinodeInstancesApi.md#GetLinodeInstance) | **Get** /linode/instances/{linodeId} | View Linode
[**GetLinodeInstances**](LinodeInstancesApi.md#GetLinodeInstances) | **Get** /linode/instances | List Linodes
[**GetLinodeStats**](LinodeInstancesApi.md#GetLinodeStats) | **Get** /linode/instances/{linodeId}/stats | View Linode Statistics
[**GetLinodeStatsByYearMonth**](LinodeInstancesApi.md#GetLinodeStatsByYearMonth) | **Get** /linode/instances/{linodeId}/stats/{year}/{month} | View Statistics (year/month)
[**GetLinodeTransfer**](LinodeInstancesApi.md#GetLinodeTransfer) | **Get** /linode/instances/{linodeId}/transfer | View Network Transfer
[**GetLinodeVolumes**](LinodeInstancesApi.md#GetLinodeVolumes) | **Get** /linode/instances/{linodeId}/volumes | List Linode&#39;s Volumes
[**MigrateLinodeInstance**](LinodeInstancesApi.md#MigrateLinodeInstance) | **Post** /linode/instances/{linodeId}/migrate | Initiate Pending Host Migration/DC Migration
[**MutateLinodeInstance**](LinodeInstancesApi.md#MutateLinodeInstance) | **Post** /linode/instances/{linodeId}/mutate | Upgrade Linode
[**RebootLinodeInstance**](LinodeInstancesApi.md#RebootLinodeInstance) | **Post** /linode/instances/{linodeId}/reboot | Reboot Linode
[**RebuildLinodeInstance**](LinodeInstancesApi.md#RebuildLinodeInstance) | **Post** /linode/instances/{linodeId}/rebuild | Rebuild Linode
[**RemoveLinodeIP**](LinodeInstancesApi.md#RemoveLinodeIP) | **Delete** /linode/instances/{linodeId}/ips/{address} | Delete IPv4 Address
[**RescueLinodeInstance**](LinodeInstancesApi.md#RescueLinodeInstance) | **Post** /linode/instances/{linodeId}/rescue | Boot Linode into Rescue Mode
[**ResetDiskPassword**](LinodeInstancesApi.md#ResetDiskPassword) | **Post** /linode/instances/{linodeId}/disks/{diskId}/password | Reset Disk Root Password
[**ResizeDisk**](LinodeInstancesApi.md#ResizeDisk) | **Post** /linode/instances/{linodeId}/disks/{diskId}/resize | Resize Disk
[**ResizeLinodeInstance**](LinodeInstancesApi.md#ResizeLinodeInstance) | **Post** /linode/instances/{linodeId}/resize | Resize Linode
[**RestoreBackup**](LinodeInstancesApi.md#RestoreBackup) | **Post** /linode/instances/{linodeId}/backups/{backupId}/restore | Restore Backup
[**ShutdownLinodeInstance**](LinodeInstancesApi.md#ShutdownLinodeInstance) | **Post** /linode/instances/{linodeId}/shutdown | Shut Down Linode
[**UpdateDisk**](LinodeInstancesApi.md#UpdateDisk) | **Put** /linode/instances/{linodeId}/disks/{diskId} | Update Disk
[**UpdateLinodeConfig**](LinodeInstancesApi.md#UpdateLinodeConfig) | **Put** /linode/instances/{linodeId}/configs/{configId} | Update Configuration Profile
[**UpdateLinodeIP**](LinodeInstancesApi.md#UpdateLinodeIP) | **Put** /linode/instances/{linodeId}/ips/{address} | Update IP Address
[**UpdateLinodeInstance**](LinodeInstancesApi.md#UpdateLinodeInstance) | **Put** /linode/instances/{linodeId} | Update Linode



## AddLinodeConfig

> LinodeConfig AddLinodeConfig(ctx, linodeId, linodeConfig)

Create Configuration Profile

Adds a new Configuration profile to a Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up Configuration profiles for. | 
**linodeConfig** | [**LinodeConfig**](LinodeConfig.md)| The parameters to set when creating the Configuration profile. This determines which kernel, devices, how much memory, etc. a Linode boots with.  | 

### Return type

[**LinodeConfig**](LinodeConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## AddLinodeDisk

> Disk AddLinodeDisk(ctx, linodeId, diskRequest)

Create Disk

Adds a new Disk to a Linode. You can optionally create a Disk from an Image (see [/images](/api/v4/images) for a list of available public images, or use one of your own), and optionally provide a StackScript to deploy with this Disk. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskRequest** | [**DiskRequest**](DiskRequest.md)| The parameters to set when creating the Disk.  | 

### Return type

[**Disk**](Disk.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## AddLinodeIP

> IpAddress AddLinodeIP(ctx, linodeId, uNKNOWNBASETYPE)

Allocate IPv4 Address

Allocates a public or private IPv4 address to a Linode. Public IP Addresses, after the one included with each Linode, incur an additional monthly charge. If you need an additional public IP Address you must request one - please [open a support ticket](/api/v4/support-tickets/#post). You may not add more than one private IPv4 address to a single Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the address you are creating. | 

### Return type

[**IpAddress**](IPAddress.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## BootLinodeInstance

> map[string]interface{} BootLinodeInstance(ctx, linodeId, optional)

Boot Linode

Boots a Linode you have permission to modify. If no parameters are given, a Config profile will be chosen for this boot based on the following criteria:  * If there is only one Config profile for this Linode, it will be used. * If there is more than one Config profile, the last booted config will be used. * If there is more than one Config profile and none were the last to be booted (because the   Linode was never booted or the last booted config was deleted) an error will be returned. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to boot. | 
 **optional** | ***BootLinodeInstanceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a BootLinodeInstanceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **inlineObject4** | [**optional.Interface of InlineObject4**](InlineObject4.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CancelBackups

> map[string]interface{} CancelBackups(ctx, linodeId)

Cancel Backups

Cancels the Backup service on the given Linode. Deletes all of this Linode's existing backups forever. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to cancel backup service for. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CloneLinodeDisk

> Disk CloneLinodeDisk(ctx, linodeId, diskId)

Clone Disk

Copies a disk, byte-for-byte, into a new Disk belonging to the same Linode. The Linode must have enough storage space available to accept a new Disk of the same size as this one or this operation will fail. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to clone. | 

### Return type

[**Disk**](Disk.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CloneLinodeInstance

> Linode CloneLinodeInstance(ctx, linodeId, inlineObject5)

Clone Linode

You can clone your Linode's existing Disks or Configuration profiles to another Linode on your Account. In order for this request to complete successfully, your User must have the `add_linodes` grant. Cloning to a new Linode will incur a charge on your Account.  If cloning to an existing Linode, any actions currently running or queued must be completed first before you can clone to it.  Up to five clone operations from any given source Linode can be run concurrently. If more concurrent clones are attempted, an HTTP 400 error will be returned by this endpoint.  Any [tags](/api/v4/tags) existing on the source Linode will be cloned to the target Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to clone. | 
**inlineObject5** | [**InlineObject5**](InlineObject5.md)|  | 

### Return type

[**Linode**](Linode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateLinodeInstance

> Linode CreateLinodeInstance(ctx, inlineObject1)

Create Linode

Creates a Linode Instance on your Account. In order for this request to complete successfully, your User must have the `add_linodes` grant. Creating a new Linode will incur a charge on your Account.  Linodes can be created using one of the available Types. See [GET /linode/types](/api/v4/linode-types) to get more information about each Type's specs and cost.  Linodes can be created in any one of our available [Regions](/api/v4/regions) for a list of available Regions you can deploy your Linode in.  Linodes can be created in a number of ways:  * Using a Linode Linux Distribution image or an Image you created based on another Linode.   * The Linode will be `running` after it completes `provisioning`.   * A default config with two Disks, one being a 512 swap disk, is created.     * `swap_size` can be used to customize the swap disk size.   * Requires a `root_pass` be supplied to use for the root User's Account.   * It is recommended to supply SSH keys for the root User using the `authorized_keys` field.   * You may also supply a list of usernames via the `authorized_users` field.     * These users must have an SSH Key associated with your Profile first. See [/profile/sshkeys](/api/v4/profile-sshkeys/#post) for more information.  * Using a StackScript.   * See [/linode/stackscripts](/api/v4/linode-stackscripts) for     a list of available StackScripts.   * The Linode will be `running` after it completes `provisioning`.   * Requires a compatible Image to be supplied.     * See [/linode/stackscript/{stackscriptId}](/api/v4/linode-stackscripts-stackscript-id) for compatible Images.   * Requires a `root_pass` be supplied to use for the root User's Account.   * It is recommended to supply SSH keys for the root User using the `authorized_keys` field.   * You may also supply a list of usernames via the `authorized_users` field.     * These users must have an SSH Key associated with your Profile first. See [/profile/sshkeys](/api/v4/profile-sshkeys/#post) for more information.  * Using one of your other Linode's backups.   * You must create a Linode large enough to accommodate the Backup's size.   * The Disks and Config will match that of the Linode that was backed up.   * The `root_pass` will match that of the Linode that was backed up.  * Create an empty Linode.   * The Linode will remain `offline` and must be manually started.     * See [POST /linode/instances/{linodeId}/boot](/api/v4/linode-instances-linode-id-boot/#post).   * Disks and Configs must be created manually.   * This is only recommended for advanced use cases.   **Important**: You must be an unrestricted User in order to add or modify tags on Linodes. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**inlineObject1** | [**InlineObject1**](InlineObject1.md)|  | 

### Return type

[**Linode**](Linode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateSnapshot

> Backup CreateSnapshot(ctx, linodeId, inlineObject2)

Create Snapshot

Creates a snapshot Backup of a Linode. ** If you already have a snapshot of this Linode, this is a destructive action. The previous snapshot will be deleted.** 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode the backups belong to. | 
**inlineObject2** | [**InlineObject2**](InlineObject2.md)|  | 

### Return type

[**Backup**](Backup.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteDisk

> map[string]interface{} DeleteDisk(ctx, linodeId, diskId)

Delete Disk

Deletes a Disk you have permission to `read_write`.  **Deleting a Disk is a destructive action and cannot be undone.** 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteLinodeConfig

> map[string]interface{} DeleteLinodeConfig(ctx, linodeId, configId)

Delete Configuration Profile

Deletes the specified Configuration profile from the specified Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode whose Configuration profile to look up. | 
**configId** | **int32**| The ID of the Configuration profile to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteLinodeInstance

> map[string]interface{} DeleteLinodeInstance(ctx, linodeId)

Delete Linode

Deletes a Linode you have permission to `read_write`.  **Deleting a Linode is a destructive action and cannot be undone.**  Additionally, deleting a Linode:    * Gives up any IP addresses the Linode was assigned.   * Deletes all Disks, Backups, Configs, etc.   * Stops billing for the Linode and its associated services. You will be billed for time used     within the billing period the Linode was active. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## EnableBackups

> map[string]interface{} EnableBackups(ctx, linodeId)

Enable Backups

Enables backups for the specified Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to enable backup service for. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetBackup

> Backup GetBackup(ctx, linodeId, backupId)

View Backup

Returns information about a Backup. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode the Backup belongs to. | 
**backupId** | **int32**| The ID of the Backup to look up. | 

### Return type

[**Backup**](Backup.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetBackups

> InlineResponse20013 GetBackups(ctx, linodeId)

List Backups

Returns information about this Linode's available backups. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode the backups belong to. | 

### Return type

[**InlineResponse20013**](inline_response_200_13.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetKernel

> Kernel GetKernel(ctx, kernelId)

View Kernel

Returns information about a single Kernel. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**kernelId** | **string**| ID of the Kernel to look up. | 

### Return type

[**Kernel**](Kernel.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetKernels

> InlineResponse20016 GetKernels(ctx, optional)

List Kernels

Lists available Kernels. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetKernelsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetKernelsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20016**](inline_response_200_16.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeConfig

> LinodeConfig GetLinodeConfig(ctx, linodeId, configId)

View Configuration Profile

Returns information about a specific Configuration profile. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode whose Configuration profile to look up. | 
**configId** | **int32**| The ID of the Configuration profile to look up. | 

### Return type

[**LinodeConfig**](LinodeConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeConfigs

> InlineResponse20014 GetLinodeConfigs(ctx, linodeId, optional)

List Configuration Profiles

Lists Configuration profiles associated with a Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up Configuration profiles for. | 
 **optional** | ***GetLinodeConfigsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLinodeConfigsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20014**](inline_response_200_14.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeDisk

> Disk GetLinodeDisk(ctx, linodeId, diskId)

View Disk

View Disk information for a Disk associated with this Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to look up. | 

### Return type

[**Disk**](Disk.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeDisks

> InlineResponse20015 GetLinodeDisks(ctx, linodeId, optional)

List Disks

View Disk information for Disks associated with this Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
 **optional** | ***GetLinodeDisksOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLinodeDisksOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20015**](inline_response_200_15.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeIP

> IpAddress GetLinodeIP(ctx, linodeId, address)

View IP Address

View information about the specified IP address associated with the specified Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to look up. | 
**address** | **string**| The IP address to look up. | 

### Return type

[**IpAddress**](IPAddress.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeIPs

> map[string]interface{} GetLinodeIPs(ctx, linodeId)

List Networking Information

Returns networking information for a single Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeInstance

> Linode GetLinodeInstance(ctx, linodeId)

View Linode

Get a specific Linode by ID.

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up | 

### Return type

[**Linode**](Linode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeInstances

> InlineResponse20012 GetLinodeInstances(ctx, optional)

List Linodes

Returns a paginated list of Linodes you have permission to view. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetLinodeInstancesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLinodeInstancesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20012**](inline_response_200_12.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeStats

> LinodeStats GetLinodeStats(ctx, linodeId)

View Linode Statistics

Returns CPU, IO, IPv4, and IPv6 statistics for your Linode for the past 24 hours. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 

### Return type

[**LinodeStats**](LinodeStats.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeStatsByYearMonth

> LinodeStats GetLinodeStatsByYearMonth(ctx, linodeId, year, month)

View Statistics (year/month)

Returns statistics for a specific month. The year/month values must be either a date in the past, or the current month. If the current month, statistics will be retrieved for the past 30 days. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**year** | **int32**| Numeric value representing the year to look up. | 
**month** | **int32**| Numeric value representing the month to look up. | 

### Return type

[**LinodeStats**](LinodeStats.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeTransfer

> map[string]interface{} GetLinodeTransfer(ctx, linodeId)

View Network Transfer

Returns a Linode's network transfer pool statistics for the current month. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeVolumes

> InlineResponse20017 GetLinodeVolumes(ctx, linodeId, optional)

List Linode's Volumes

View Block Storage Volumes attached to this Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
 **optional** | ***GetLinodeVolumesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLinodeVolumesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20017**](inline_response_200_17.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## MigrateLinodeInstance

> map[string]interface{} MigrateLinodeInstance(ctx, linodeId, optional)

Initiate Pending Host Migration/DC Migration

Initiate a pending host migration that has been scheduled by Linode or initiate a cross data center (DC) migration.  A list of pending migrations, if any, can be accessed from [GET /account/notifications](/api/v4/account-notifications). When the migration begins, your Linode will be shutdown if not already off. If the migration initiated the shutdown, it will reboot the Linode when completed.  To initiate a cross DC migration, you must pass a `region` parameter to the request body specifying the target data center region. You can view a list of all available regions and their feature capabilities from [GET /regions](/api/v4/regions). If your Linode has a DC migration already queued or you have initiated a previously scheduled migration, you will not be able to initiate a DC migration until it has completed.  **Note:** Next Generation Network (NGN) data centers do not support IPv6 `/116` pools or IP Failover. If you have these features enabled on your Linode and attempt to migrate to an NGN data center, the migration will not initiate. If a Linode cannot be migrated because of an incompatibility, you will be prompted to select a different data center or contact support. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to migrate. | 
 **optional** | ***MigrateLinodeInstanceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a MigrateLinodeInstanceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## MutateLinodeInstance

> map[string]interface{} MutateLinodeInstance(ctx, linodeId, optional)

Upgrade Linode

Linodes created with now-deprecated Types are entitled to a free upgrade to the next generation. A mutating Linode will be allocated any new resources the upgraded Type provides, and will be subsequently restarted if it was currently running. If any actions are currently running or queued, those actions must be completed first before you can initiate a mutate. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to mutate. | 
 **optional** | ***MutateLinodeInstanceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a MutateLinodeInstanceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **inlineObject6** | [**optional.Interface of InlineObject6**](InlineObject6.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RebootLinodeInstance

> map[string]interface{} RebootLinodeInstance(ctx, linodeId, optional)

Reboot Linode

Reboots a Linode you have permission to modify. If any actions are currently running or queued, those actions must be completed first before you can initiate a reboot. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the linode to reboot. | 
 **optional** | ***RebootLinodeInstanceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a RebootLinodeInstanceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Optional reboot parameters. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RebuildLinodeInstance

> Linode RebuildLinodeInstance(ctx, linodeId, uNKNOWNBASETYPE)

Rebuild Linode

Rebuilds a Linode you have the `read_write` permission to modify. A rebuild will first shut down the Linode, delete all disks and configs on the Linode, and then deploy a new `image` to the Linode with the given attributes. Additionally:    * Requires an `image` be supplied.   * Requires a `root_pass` be supplied to use for the root User's Account.   * It is recommended to supply SSH keys for the root User using the     `authorized_keys` field. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to rebuild. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The requested state your Linode will be rebuilt into. | 

### Return type

[**Linode**](Linode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RemoveLinodeIP

> map[string]interface{} RemoveLinodeIP(ctx, linodeId, address)

Delete IPv4 Address

Deletes a public IPv4 address associated with this Linode. This will fail if it is the Linode's last remaining public IPv4 address. Private IPv4 addresses cannot be removed via this endpoint. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to look up. | 
**address** | **string**| The IP address to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RescueLinodeInstance

> map[string]interface{} RescueLinodeInstance(ctx, linodeId, optional)

Boot Linode into Rescue Mode

Rescue Mode is a safe environment for performing many system recovery and disk management tasks. Rescue Mode is based on the Finnix recovery distribution, a self-contained and bootable Linux distribution. You can also use Rescue Mode for tasks other than disaster recovery, such as formatting disks to use different filesystems, copying data between disks, and downloading files from a disk via SSH and SFTP. * Note that \"sdh\" is reserved and unavailable during rescue. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to rescue. | 
 **optional** | ***RescueLinodeInstanceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a RescueLinodeInstanceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **inlineObject7** | [**optional.Interface of InlineObject7**](InlineObject7.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ResetDiskPassword

> map[string]interface{} ResetDiskPassword(ctx, linodeId, diskId, uNKNOWNBASETYPE)

Reset Disk Root Password

Resets the password of a Disk you have permission to `read_write`. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to look up. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The new password. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ResizeDisk

> map[string]interface{} ResizeDisk(ctx, linodeId, diskId, uNKNOWNBASETYPE)

Resize Disk

Resizes a Disk you have permission to `read_write`. The Linode this Disk is attached to must be shut down for resizing to take effect. If you are resizing the Disk to a smaller size, it cannot be made smaller than what is required by the total size of the files current on the Disk. The Disk must not be in use. If the Disk is in use, the request will succeed but the resize will ultimately fail. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to look up. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The new size of the Disk. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ResizeLinodeInstance

> map[string]interface{} ResizeLinodeInstance(ctx, linodeId, inlineObject8)

Resize Linode

Resizes a Linode you have the `read_write` permission to a different Type. If any actions are currently running or queued, those actions must be completed first before you can initiate a resize. Additionally, the following criteria must be met in order to resize a Linode:    * The Linode must not have a pending migration.   * Your Account cannot have an outstanding balance.   * The Linode must not have more disk allocation than the new Type allows.     * In that situation, you must first delete or resize the disk to be smaller. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to resize. | 
**inlineObject8** | [**InlineObject8**](InlineObject8.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RestoreBackup

> map[string]interface{} RestoreBackup(ctx, linodeId, backupId, inlineObject3)

Restore Backup

Restores a Linode's Backup to the specified Linode. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode that the Backup belongs to. | 
**backupId** | **int32**| The ID of the Backup to restore. | 
**inlineObject3** | [**InlineObject3**](InlineObject3.md)|  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ShutdownLinodeInstance

> map[string]interface{} ShutdownLinodeInstance(ctx, linodeId)

Shut Down Linode

Shuts down a Linode you have permission to modify. If any actions are currently running or queued, those actions must be completed first before you can initiate a shutdown. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to shutdown. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateDisk

> Disk UpdateDisk(ctx, linodeId, diskId, disk)

Update Disk

Updates a Disk that you have permission to `read_write`. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up. | 
**diskId** | **int32**| ID of the Disk to look up. | 
**disk** | [**Disk**](Disk.md)| Updates the parameters of a single Disk.  | 

### Return type

[**Disk**](Disk.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateLinodeConfig

> LinodeConfig UpdateLinodeConfig(ctx, linodeId, configId, uNKNOWNBASETYPE)

Update Configuration Profile

Updates a Configuration profile. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode whose Configuration profile to look up. | 
**configId** | **int32**| The ID of the Configuration profile to look up. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The Configuration profile parameters to modify. | 

### Return type

[**LinodeConfig**](LinodeConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateLinodeIP

> IpAddress UpdateLinodeIP(ctx, linodeId, address, optional)

Update IP Address

Updates a particular IP Address associated with this Linode. Only allows setting/resetting reverse DNS. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The ID of the Linode to look up. | 
**address** | **string**| The IP address to look up. | 
 **optional** | ***UpdateLinodeIPOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a UpdateLinodeIPOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The information to update for the IP address. | 

### Return type

[**IpAddress**](IPAddress.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateLinodeInstance

> Linode UpdateLinodeInstance(ctx, linodeId, linode)

Update Linode

Updates a Linode that you have permission to `read_write`.  **Important**: You must be an unrestricted User in order to add or modify tags on Linodes. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| ID of the Linode to look up | 
**linode** | [**Linode**](Linode.md)| Any field that is not marked as &#x60;readOnly&#x60; may be updated. Fields that are marked &#x60;readOnly&#x60; will be ignored. If any updated field fails to pass validation, the Linode will not be updated.  | 

### Return type

[**Linode**](Linode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

