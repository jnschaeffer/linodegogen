# Domain

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Domain&#39;s unique ID | [readonly] 
**Type** | **string** | If this Domain represents the authoritative source of information for the domain it describes, or if it is a read-only copy of a master (also called a slave).  | 
**Domain** | **string** | The domain this Domain represents. Domain labels cannot be longer than 63 characters and must conform to [RFC1035](https://tools.ietf.org/html/rfc1035). Domains must be unique on Linode&#39;s platform, including across different Linode accounts; there cannot be two Domains representing the same domain.  | 
**Group** | **string** | The group this Domain belongs to.  This is for display purposes only.  | [optional] 
**Status** | **string** | Used to control whether this Domain is currently being rendered.  | [optional] 
**Description** | **string** | A description for this Domain. This is for display purposes only.  | [optional] 
**SoaEmail** | **string** | Start of Authority email address. This is required for master Domains.  | [optional] 
**RetrySec** | **int32** | The interval, in seconds, at which a failed refresh should be retried. Valid values are 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value.  | [optional] 
**MasterIps** | **[]string** | The IP addresses representing the master DNS for this Domain.  | [optional] 
**AxfrIps** | **[]string** | The list of IPs that may perform a zone transfer for this Domain. This is potentially dangerous, and should be set to an empty list unless you intend to use it.  | [optional] 
**ExpireSec** | **int32** | The amount of time in seconds that may pass before this Domain is no longer authoritative. Valid values are 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value.  | [optional] 
**RefreshSec** | **int32** | The amount of time in seconds before this Domain should be refreshed. Valid values are 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value.  | [optional] 
**TtlSec** | **int32** | \&quot;Time to Live\&quot; - the amount of time in seconds that this Domain&#39;s records may be cached by resolvers or other domain servers. * Valid values are 0, 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value. * ttl_sec will default to 0 if no value is provided. * A value of 0 is equivalent to a value of 86400.  | [optional] 
**Tags** | **[]string** | An array of tags applied to this object.  Tags are for organizational purposes only.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


