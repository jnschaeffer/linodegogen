# \LinodeTypesApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**GetLinodeType**](LinodeTypesApi.md#GetLinodeType) | **Get** /linode/types/{typeId} | View Type
[**GetLinodeTypes**](LinodeTypesApi.md#GetLinodeTypes) | **Get** /linode/types | List Types



## GetLinodeType

> LinodeType GetLinodeType(ctx, typeId)

View Type

Returns information about a specific Linode Type, including pricing and specifications. This is used when [creating](/api/v4/linode-instances/#post) or [resizing](/api/v4/linode-instances-linode-id-resize/#post) Linodes. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**typeId** | **string**| The ID of the Linode Type to look up. | 

### Return type

[**LinodeType**](LinodeType.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLinodeTypes

> InlineResponse20019 GetLinodeTypes(ctx, )

List Types

Returns collection of Linode Types, including pricing and specifications for each Type. These are used when [creating](/api/v4/linode-instances/#post) or [resizing](/api/v4/linode-instances-linode-id-resize/#post) Linodes. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20019**](inline_response_200_19.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

