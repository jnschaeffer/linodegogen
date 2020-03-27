# LinodeConfigHelpers

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**UpdatedbDisabled** | **bool** | Disables updatedb cron job to avoid disk thrashing. | [optional] 
**Distro** | **bool** | Helps maintain correct inittab/upstart console device. | [optional] 
**ModulesDep** | **bool** | Creates a modules dependency file for the Kernel you run. | [optional] 
**Network** | **bool** | Automatically configures static networking. | [optional] 
**DevtmpfsAutomount** | **bool** | Populates the /dev directory early during boot without udev.  Defaults to false.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


