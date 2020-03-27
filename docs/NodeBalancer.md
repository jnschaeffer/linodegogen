# NodeBalancer

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This NodeBalancer&#39;s unique ID.  | [optional] [readonly] 
**Label** | **string** | This NodeBalancer&#39;s label. These must be unique on your Account.  | [optional] 
**Region** | **string** | The Region where this NodeBalancer is located. NodeBalancers only support backends in the same Region.  | [optional] [readonly] 
**Hostname** | **string** | This NodeBalancer&#39;s hostname, ending with _.nodebalancer.linode.com_  | [optional] [readonly] 
**Ipv4** | **string** | This NodeBalancer&#39;s public IPv4 address.  | [optional] [readonly] 
**Ipv6** | Pointer to **string** | This NodeBalancer&#39;s public IPv6 address.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this NodeBalancer was created.  | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | When this NodeBalancer was last updated.  | [optional] [readonly] 
**ClientConnThrottle** | **int32** | Throttle connections per second.  Set to 0 (zero) to disable throttling.  | [optional] 
**Transfer** | [**NodeBalancerTransfer**](NodeBalancer_transfer.md) |  | [optional] 
**Tags** | **[]string** | An array of Tags applied to this object.  Tags are for organizational purposes only.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


