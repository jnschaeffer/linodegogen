# Linode

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Label** | [**map[string]interface{}**](map[string]interface{}.md) | The Linode&#39;s label is for display purposes only. If no label is provided for a Linode, a default will be assigned. Linode labels have the following constraints:    * Must start with an alpha character.   * May only consist of alphanumeric characters, dashes (&#x60;-&#x60;), underscores (&#x60;_&#x60;) or periods (&#x60;.&#x60;).   * Cannot have two dashes (&#x60;--&#x60;), underscores (&#x60;__&#x60;) or periods (&#x60;..&#x60;) in a row.  | [optional] 
**Region** | [**map[string]interface{}**](map[string]interface{}.md) | This is the location where the Linode was deployed. A Linode&#39;s region can only be changed by initiating a [cross data center migration](/api/v4/linode-instances-linode-id-migrate/#post).  | [optional] [readonly] 
**Image** | Pointer to [**Image**](image.md) |  | [optional] [readonly] 
**Type** | [**map[string]interface{}**](map[string]interface{}.md) | This is the [Linode Type](/api/v4/linode-types) that this Linode was deployed with. To change a Linode&#39;s Type, use [POST /linode/instances/{linodeId}/resize](/api/v4/linode-instances-linode-id-resize/#post).  | [optional] [readonly] 
**Group** | **string** | A deprecated property denoting a group label for this Linode.  | [optional] 
**Tags** | **[]string** | An array of tags applied to this object.  Tags are for organizational purposes only.  | [optional] 
**Id** | **int32** | This Linode&#39;s ID which must be provided for all operations impacting this Linode.  | [optional] [readonly] 
**Status** | **string** | A brief description of this Linode&#39;s current state. This field may change without direct action from you. For example, when a Linode goes into maintenance mode its status will display \&quot;stopped\&quot;.  | [optional] [readonly] 
**Hypervisor** | **string** | The virtualization software powering this Linode.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this Linode was created. | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this Linode was last updated. | [optional] [readonly] 
**Ipv4** | **[]string** | This Linode&#39;s IPv4 Addresses. Each Linode is assigned a single public IPv4 address upon creation, and may get a single private IPv4 address if needed. You may need to [open a support ticket](/api/v4/support-tickets/#post) to get additional IPv4 addresses.  IPv4 addresses may be reassigned between your Linodes, or shared with other Linodes. See the [/networking](#tag/networking) endpoints for details.  | [optional] [readonly] 
**Ipv6** | **string** | This Linode&#39;s IPv6 SLAAC addresses. This address is specific to a Linode, and may not be shared. If the Linode has not been assigned an IPv6 address, the return value will be &#x60;null&#x60;.  | [optional] [readonly] 
**Specs** | [**map[string]interface{}**](map[string]interface{}.md) | Information about the resources available to this Linode. | [optional] [readonly] 
**Alerts** | [**map[string]interface{}**](map[string]interface{}.md) |  | [optional] 
**Backups** | [**map[string]interface{}**](map[string]interface{}.md) | Information about this Linode&#39;s backups status. For information about available backups, see [/linode/instances/{linodeId}/backups](/api/v4/linode-instances-linode-id-backups).  | [optional] 
**WatchdogEnabled** | **bool** | The watchdog, named Lassie, is a Shutdown Watchdog that monitors your Linode and will reboot it if it powers off unexpectedly. It works by issuing a boot job when your Linode powers off without a shutdown job being responsible. To prevent a loop, Lassie will give up if there have been more than 5 boot jobs issued within 15 minutes.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


