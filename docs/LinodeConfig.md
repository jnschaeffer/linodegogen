# LinodeConfig

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The ID of this Config. | [optional] [readonly] 
**Kernel** | **string** | A Kernel ID to boot a Linode with. Defaults to \&quot;linode/latest-64bit\&quot;. | [optional] 
**Comments** | Pointer to **string** | Optional field for arbitrary User comments on this Config. | [optional] 
**MemoryLimit** | **int32** | Defaults to the total RAM of the Linode.  | [optional] 
**RunLevel** | **string** | Defines the state of your Linode after booting. Defaults to &#x60;default&#x60;.  | [optional] 
**VirtMode** | **string** | Controls the virtualization mode. Defaults to &#x60;paravirt&#x60;. * &#x60;paravirt&#x60; is suitable for most cases. Linodes running in paravirt mode   share some qualities with the host, ultimately making it run faster since   there is less transition between it and the host. * &#x60;full_virt&#x60; affords more customization, but is slower because 100% of the VM   is virtualized.  | [optional] 
**Helpers** | [**LinodeConfigHelpers**](LinodeConfig_helpers.md) |  | [optional] 
**Label** | **string** | The Config&#39;s label is for display purposes only.  | 
**Devices** | [**Devices**](Devices.md) |  | 
**RootDevice** | **string** | The root device to boot. * If no value or an invalid value is provided, root device will default to &#x60;/dev/sda&#x60;. * If the device specified at the root device location is not mounted, the Linode will not boot until a device is mounted.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


