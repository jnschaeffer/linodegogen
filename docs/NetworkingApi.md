# \NetworkingApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**AllocateIP**](NetworkingApi.md#AllocateIP) | **Post** /networking/ips | Allocate IP Address
[**AssignIPs**](NetworkingApi.md#AssignIPs) | **Post** /networking/ipv4/assign | Assign IPs to Linodes
[**GetIP**](NetworkingApi.md#GetIP) | **Get** /networking/ips/{address} | View IP Address
[**GetIPs**](NetworkingApi.md#GetIPs) | **Get** /networking/ips | List IP Addresses
[**GetIPv6Pools**](NetworkingApi.md#GetIPv6Pools) | **Get** /networking/ipv6/pools | List IPv6 Pools
[**GetIPv6Ranges**](NetworkingApi.md#GetIPv6Ranges) | **Get** /networking/ipv6/ranges | List IPv6 Ranges
[**ShareIPs**](NetworkingApi.md#ShareIPs) | **Post** /networking/ipv4/share | Configure IP Sharing
[**UpdateIP**](NetworkingApi.md#UpdateIP) | **Put** /networking/ips/{address} | Update IP Address RDNS



## AllocateIP

> IpAddress AllocateIP(ctx, uNKNOWNBASETYPE)

Allocate IP Address

Allocates a new IPv4 Address on your Account. The Linode must be configured to support additional addresses - please [open a support ticket](/api/v4/support-tickets/#post) requesting additional addresses before attempting allocation. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
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


## AssignIPs

> map[string]interface{} AssignIPs(ctx, uNKNOWNBASETYPE)

Assign IPs to Linodes

Assign multiple IPs to multiple Linodes in one Region. This allows swapping, shuffling, or otherwise reorganizing IPv4 Addresses to your Linodes.  When the assignment is finished, all Linodes must end up with at least one public IPv4 and no more than one private IPv4. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about what IPv4 address to assign, and to which Linode.  | 

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


## GetIP

> IpAddress GetIP(ctx, address)

View IP Address

Returns information about a single IP Address on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**address** | **string**| The address to operate on. | 

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


## GetIPs

> InlineResponse20034 GetIPs(ctx, )

List IP Addresses

Returns a paginated list of IP Addresses on your Account, excluding private addresses. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20034**](inline_response_200_34.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetIPv6Pools

> InlineResponse20035 GetIPv6Pools(ctx, optional)

List IPv6 Pools

Displays the IPv6 pools on your Account. A pool of IPv6 addresses are routed to all of your Linodes in a single [Region](https://developers.linode.com/api/v4/regions). Any Linode on your Account may bring up any address in this pool at any time, with no external configuration required. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetIPv6PoolsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetIPv6PoolsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20035**](inline_response_200_35.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetIPv6Ranges

> InlineResponse20036 GetIPv6Ranges(ctx, optional)

List IPv6 Ranges

Displays the IPv6 ranges on your Account. A range of IPv6 addresses is routed to a single Linode in a given [Region](https://developers.linode.com/api/v4/regions). Your Linode is responsible for routing individual addresses in the range, or handling traffic for all the addresses in the range. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetIPv6RangesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetIPv6RangesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20036**](inline_response_200_36.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ShareIPs

> map[string]interface{} ShareIPs(ctx, uNKNOWNBASETYPE)

Configure IP Sharing

Configure shared IPs.  A shared IP may be brought up on a Linode other than the one it lists in its response.  This can be used to allow one Linode to begin serving requests should another become unresponsive. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about what IPs to share with which Linode. | 

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


## UpdateIP

> IpAddress UpdateIP(ctx, address, ipAddress)

Update IP Address RDNS

Sets RDNS on an IP Address. Forward DNS must already be set up for reverse DNS to be applied. If you set the RDNS to `null` for public IPv4 addresses, it will be reset to the default _members.linode.com_ RDNS value. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**address** | **string**| The address to operate on. | 
**ipAddress** | [**IpAddress**](IpAddress.md)| The information to update. | 

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

