# \ImagesApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateImage**](ImagesApi.md#CreateImage) | **Post** /images | Create Image
[**DeleteImage**](ImagesApi.md#DeleteImage) | **Delete** /images/{imageId} | Delete Image
[**GetImage**](ImagesApi.md#GetImage) | **Get** /images/{imageId} | View Image
[**GetImages**](ImagesApi.md#GetImages) | **Get** /images | List Images
[**UpdateImage**](ImagesApi.md#UpdateImage) | **Put** /images/{imageId} | Update Image



## CreateImage

> ImagePrivate CreateImage(ctx, optional)

Create Image

Creates a private gold-master Image from a Linode Disk. There is no additional charge to store Images for Linode users. Images are limited to three per Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateImageOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateImageOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the Image to create. | 

### Return type

[**ImagePrivate**](ImagePrivate.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteImage

> map[string]interface{} DeleteImage(ctx, imageId)

Delete Image

Deletes a private Image you have permission to `read_write`.   **Deleting an Image is a destructive action and cannot be undone.** 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**imageId** | **string**| ID of the Image to look up. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetImage

> ImagePrivate GetImage(ctx, imageId)

View Image

Get information about a single Image. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**imageId** | **string**| ID of the Image to look up. | 

### Return type

[**ImagePrivate**](ImagePrivate.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetImages

> InlineResponse20011 GetImages(ctx, optional)

List Images

Returns a paginated list of Images.  * Calling this endpoint without authentication returns all public Images. * Authentication is required to return a combined paginated list of all public and   your private Images. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetImagesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetImagesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20011**](inline_response_200_11.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateImage

> ImagePrivate UpdateImage(ctx, imageId, imagePrivate)

Update Image

Updates a private Image that you have permission to `read_write`. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**imageId** | **string**| ID of the Image to look up. | 
**imagePrivate** | [**ImagePrivate**](ImagePrivate.md)| The fields to update.  | 

### Return type

[**ImagePrivate**](ImagePrivate.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

