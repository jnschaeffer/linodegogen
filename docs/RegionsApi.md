# \RegionsApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**GetRegion**](RegionsApi.md#GetRegion) | **Get** /regions/{regionId} | View Region
[**GetRegions**](RegionsApi.md#GetRegions) | **Get** /regions | List Regions



## GetRegion

> Region GetRegion(ctx, regionId)

View Region

Returns a single Region. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**regionId** | **string**| ID of the Region to look up. | 

### Return type

[**Region**](Region.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetRegions

> InlineResponse20047 GetRegions(ctx, )

List Regions

Lists the Regions available for Linode services. Not all services are guaranteed to be available in all Regions. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20047**](inline_response_200_47.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

