# \StackScriptsApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**AddStackScript**](StackScriptsApi.md#AddStackScript) | **Post** /linode/stackscripts | Create StackScript
[**DeleteStackScript**](StackScriptsApi.md#DeleteStackScript) | **Delete** /linode/stackscripts/{stackscriptId} | Delete StackScript
[**GetStackScript**](StackScriptsApi.md#GetStackScript) | **Get** /linode/stackscripts/{stackscriptId} | View StackScript
[**GetStackScripts**](StackScriptsApi.md#GetStackScripts) | **Get** /linode/stackscripts | List StackScripts
[**UpdateStackScript**](StackScriptsApi.md#UpdateStackScript) | **Put** /linode/stackscripts/{stackscriptId} | Update StackScript



## AddStackScript

> StackScript AddStackScript(ctx, uNKNOWNBASETYPE)

Create StackScript

Creates a StackScript in your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The properties to set for the new StackScript. | 

### Return type

[**StackScript**](StackScript.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteStackScript

> map[string]interface{} DeleteStackScript(ctx, stackscriptId)

Delete StackScript

Deletes a private StackScript you have permission to `read_write`. You cannot delete a public StackScript. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**stackscriptId** | **string**| The ID of the StackScript to look up. | 

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


## GetStackScript

> StackScript GetStackScript(ctx, stackscriptId)

View StackScript

Returns all of the information about a specified StackScript, including the contents of the script. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**stackscriptId** | **string**| The ID of the StackScript to look up. | 

### Return type

[**StackScript**](StackScript.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetStackScripts

> InlineResponse20018 GetStackScripts(ctx, optional)

List StackScripts

If the request is not authenticated, only public StackScripts are returned.  For more information on StackScripts, please read our guide: <a target=\"_top\" href=\"https://linode.com/docs/platform/stackscripts/\">Automate Deployment with StackScripts</a>. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetStackScriptsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetStackScriptsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20018**](inline_response_200_18.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateStackScript

> StackScript UpdateStackScript(ctx, stackscriptId, optional)

Update StackScript

Updates a StackScript.  **Once a StackScript is made public, it cannot be made private.** 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**stackscriptId** | **string**| The ID of the StackScript to look up. | 
 **optional** | ***UpdateStackScriptOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a UpdateStackScriptOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **stackScript** | [**optional.Interface of StackScript**](StackScript.md)| The fields to update. | 

### Return type

[**StackScript**](StackScript.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

