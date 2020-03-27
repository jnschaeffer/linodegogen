# DomainRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Record&#39;s unique ID. | [optional] [readonly] 
**Type** | **string** | The type of Record this is in the DNS system. For example, A records associate a domain name with an IPv4 address, and AAAA records associate a domain name with an IPv6 address.  | [optional] 
**Name** | **string** | The name of this Record. This field&#39;s actual usage depends on the type of record this represents. For A and AAAA records, this is the subdomain being associated with an IP address.  | [optional] 
**Target** | **string** | The target for this Record. This field&#39;s actual usage depends on the type of record this represents. For A and AAAA records, this is the address the named Domain should resolve to.  | [optional] 
**Priority** | **int32** | The priority of the target host. Lower values are preferred.  | [optional] 
**Weight** | **int32** | The relative weight of this Record. Higher values are preferred.  | [optional] 
**Port** | **int32** | The port this Record points to.  | [optional] 
**Service** | Pointer to **string** | The service this Record identified. Only valid for SRV records.  | [optional] 
**Protocol** | Pointer to **string** | The protocol this Record&#39;s service communicates with. Only valid for SRV records.  | [optional] 
**TtlSec** | **int32** | \&quot;Time to Live\&quot; - the amount of time in seconds that this Domain&#39;s records may be cached by resolvers or other domain servers. Valid values are 300, 3600, 7200, 14400, 28800, 57600, 86400, 172800, 345600, 604800, 1209600, and 2419200 - any other value will be rounded to the nearest valid value.  | [optional] 
**Tag** | Pointer to **string** | The tag portion of a CAA record. It is invalid to set this on other record types.  | [optional] 
**Created** | [**time.Time**](time.Time.md) | When this Domain Record was created. | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this Domain Record was last updated. | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


