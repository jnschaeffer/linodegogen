# \LongviewApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateLongviewClient**](LongviewApi.md#CreateLongviewClient) | **Post** /longview/clients | Create Longview Client
[**DeleteLongviewClient**](LongviewApi.md#DeleteLongviewClient) | **Delete** /longview/clients/{clientId} | Delete Longview Client
[**GetLongviewClient**](LongviewApi.md#GetLongviewClient) | **Get** /longview/clients/{clientId} | View Longview Client
[**GetLongviewClients**](LongviewApi.md#GetLongviewClients) | **Get** /longview/clients | List Longview Clients
[**GetLongviewSubscription**](LongviewApi.md#GetLongviewSubscription) | **Get** /longview/subscriptions/{subscriptionId} | View Longview Subscription
[**GetLongviewSubscriptions**](LongviewApi.md#GetLongviewSubscriptions) | **Get** /longview/subscriptions | List Longview Subscriptions
[**UpdateLongviewClient**](LongviewApi.md#UpdateLongviewClient) | **Put** /longview/clients/{clientId} | Update Longview Client



## CreateLongviewClient

> LongviewClient CreateLongviewClient(ctx, longviewClient)

Create Longview Client

Creates a Longview Client.  This Client will not begin monitoring the status of your server until you configure the Longview Client application on your Linode using the returning `install_code` and `api_key`. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**longviewClient** | [**LongviewClient**](LongviewClient.md)| Information about the LongviewClient to create. | 

### Return type

[**LongviewClient**](LongviewClient.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteLongviewClient

> map[string]interface{} DeleteLongviewClient(ctx, clientId)

Delete Longview Client

Deletes a Longview Client from your Account.  **All information stored for this client will be lost.**  This _does not_ uninstall the Longview Client application for your Linode - you must do that manually. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clientId** | **int32**| The Longview Client ID to access. | 

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


## GetLongviewClient

> LongviewClient GetLongviewClient(ctx, clientId)

View Longview Client

Returns a single Longview Client you can access. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clientId** | **int32**| The Longview Client ID to access. | 

### Return type

[**LongviewClient**](LongviewClient.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLongviewClients

> InlineResponse20025 GetLongviewClients(ctx, optional)

List Longview Clients

Returns a paginated list of Longview Clients you have access to. Longview Client is used to monitor stats on your Linode with the help of the Longview Client application. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetLongviewClientsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLongviewClientsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20025**](inline_response_200_25.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLongviewSubscription

> LongviewSubscription GetLongviewSubscription(ctx, subscriptionId)

View Longview Subscription

Returns a single LongviewSubscription object.  This is a public endpoint and requires no authentication. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**subscriptionId** | **string**| The Longview Subscription to look up. | 

### Return type

[**LongviewSubscription**](LongviewSubscription.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLongviewSubscriptions

> InlineResponse20026 GetLongviewSubscriptions(ctx, optional)

List Longview Subscriptions

Returns a paginated list of available Longview Subscriptions. This is a public endpoint and requires no authentication. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetLongviewSubscriptionsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetLongviewSubscriptionsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20026**](inline_response_200_26.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateLongviewClient

> LongviewClient UpdateLongviewClient(ctx, clientId, longviewClient)

Update Longview Client

Updates a Longview Client.  This cannot update how it monitors your server; use the Longview Client application on your Linode for monitoring configuration. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clientId** | **int32**| The Longview Client ID to access. | 
**longviewClient** | [**LongviewClient**](LongviewClient.md)| The fields to update. | 

### Return type

[**LongviewClient**](LongviewClient.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

