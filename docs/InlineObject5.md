# InlineObject5

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Region** | **string** | This is the Region where the Linode will be deployed. To view all available Regions you can deploy to see [/regions](/api/v4/regions). * Region can only be provided when cloning to a new Linode.  | 
**Type** | **string** | A Linode&#39;s Type determines what resources are available to it, including disk space, memory, and virtual cpus. The amounts available to a specific Linode are returned as &#x60;specs&#x60; on the Linode object.  To view all available Linode Types you can deploy with see [/linode/types](/api/v4/linode-types).  * Type can only be provided when cloning to a new Linode.  | 
**LinodeId** | **int32** | If an existing Linode is to be the target for the clone, the ID of that Linode. The existing Linode must have enough resources to accept the clone.  | [optional] 
**Label** | **string** | The label to assign this Linode when cloning to a new Linode. * Can only be provided when cloning to a new Linode. * Defaults to \&quot;linode\&quot;.  | [optional] 
**Group** | **string** | A label used to group Linodes for display. Linodes are not required to have a group.  | [optional] 
**BackupsEnabled** | **bool** | If this field is set to &#x60;true&#x60;, the created Linode will automatically be enrolled in the Linode Backup service. This will incur an additional charge. Pricing is included in the response from [/linodes/types](/api/v4/linode-types).  * Can only be included when cloning to a new Linode.  | [optional] 
**Disks** | **[]int32** | An array of disk IDs. * If the &#x60;disks&#x60; parameter **is not provided**, then **no extra disks will be cloned** from the source Linode. All disks associated with the configuration profiles specified by the &#x60;configs&#x60; parameter will still be cloned. * **If an empty array is provided** for the &#x60;disks&#x60; parameter, then **no extra disks will be cloned** from the source Linode. All disks associated with the configuration profiles specified by the &#x60;configs&#x60; parameter will still be cloned. * **If a non-empty array is provided** for the &#x60;disks&#x60; parameter, then **the disks specified in the array will be cloned** from the source Linode, in addition to any disks associated with the configuration profiles specified by the &#x60;configs&#x60; parameter.  | [optional] 
**Configs** | **[]int32** | An array of configuration profile IDs. * If the &#x60;configs&#x60; parameter **is not provided**, then **all configuration profiles and their associated disks will be cloned** from the source Linode. Any disks specified by the &#x60;disks&#x60; parameter will also be cloned. * **If an empty array is provided** for the &#x60;configs&#x60; parameter, then **no configuration profiles (nor their associated disks) will be cloned** from the source Linode. Any disks specified by the &#x60;disks&#x60; parameter will still be cloned. * **If a non-empty array is provided** for the &#x60;configs&#x60; parameter, then **the configuration profiles specified in the array (and their associated disks) will be cloned** from the source Linode. Any disks specified by the &#x60;disks&#x60; parameter will also be cloned.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


