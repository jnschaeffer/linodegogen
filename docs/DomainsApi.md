# \DomainsApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CloneDomain**](DomainsApi.md#CloneDomain) | **Post** /domains/{domainId}/clone | Clone Domain
[**CreateDomain**](DomainsApi.md#CreateDomain) | **Post** /domains | Create Domain
[**CreateDomainRecord**](DomainsApi.md#CreateDomainRecord) | **Post** /domains/{domainId}/records | Create Domain Record
[**DeleteDomain**](DomainsApi.md#DeleteDomain) | **Delete** /domains/{domainId} | Delete Domain
[**DeleteDomainRecord**](DomainsApi.md#DeleteDomainRecord) | **Delete** /domains/{domainId}/records/{recordId} | Delete Domain Record
[**GetDomain**](DomainsApi.md#GetDomain) | **Get** /domains/{domainId} | View Domain
[**GetDomainRecord**](DomainsApi.md#GetDomainRecord) | **Get** /domains/{domainId}/records/{recordId} | View Domain Record
[**GetDomainRecords**](DomainsApi.md#GetDomainRecords) | **Get** /domains/{domainId}/records | List Domain Records
[**GetDomains**](DomainsApi.md#GetDomains) | **Get** /domains | List Domains
[**ImportDomain**](DomainsApi.md#ImportDomain) | **Post** /domains/import | Import Domain
[**UpdateDomain**](DomainsApi.md#UpdateDomain) | **Put** /domains/{domainId} | Update Domain
[**UpdateDomainRecord**](DomainsApi.md#UpdateDomainRecord) | **Put** /domains/{domainId}/records/{recordId} | Update Domain Record



## CloneDomain

> Domain CloneDomain(ctx, domainId, inlineObject)

Clone Domain

Clones a Domain and all associated DNS records from a Domain that is registered in Linode's DNS manager. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **string**| ID of the Domain to clone. | 
**inlineObject** | [**InlineObject**](InlineObject.md)|  | 

### Return type

[**Domain**](Domain.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateDomain

> Domain CreateDomain(ctx, domain)

Create Domain

Adds a new Domain to Linode's DNS Manager. Linode is not a registrar, and you must own the domain before adding it here. Be sure to point your registrar to Linode's nameservers so that the records hosted here are used. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domain** | [**Domain**](Domain.md)| Information about the domain you are registering. | 

### Return type

[**Domain**](Domain.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateDomainRecord

> DomainRecord CreateDomainRecord(ctx, domainId, uNKNOWNBASETYPE)

Create Domain Record

Adds a new Domain Record to the zonefile this Domain represents. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain we are accessing Records for. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the new Record to add.  | 

### Return type

[**DomainRecord**](DomainRecord.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteDomain

> map[string]interface{} DeleteDomain(ctx, domainId)

Delete Domain

Deletes a Domain from Linode's DNS Manager. The Domain will be removed from Linode's nameservers shortly after this operation completes. This also deletes all associated Domain Records. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain to access. | 

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


## DeleteDomainRecord

> map[string]interface{} DeleteDomainRecord(ctx, domainId, recordId)

Delete Domain Record

Deletes a Record on this Domain. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain whose Record you are accessing. | 
**recordId** | **int32**| The ID of the Record you are accessing. | 

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


## GetDomain

> Domain GetDomain(ctx, domainId)

View Domain

This is a single Domain that you have registered in Linode's DNS Manager. Linode is not a registrar, and in order for this Domain record to work you must own the domain and point your registrar at Linode's nameservers. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain to access. | 

### Return type

[**Domain**](Domain.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDomainRecord

> DomainRecord GetDomainRecord(ctx, domainId, recordId)

View Domain Record

View a single Record on this Domain. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain whose Record you are accessing. | 
**recordId** | **int32**| The ID of the Record you are accessing. | 

### Return type

[**DomainRecord**](DomainRecord.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDomainRecords

> InlineResponse20010 GetDomainRecords(ctx, domainId, optional)

List Domain Records

Returns a paginated list of Records configured on a Domain in Linode's DNS Manager. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain we are accessing Records for. | 
 **optional** | ***GetDomainRecordsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetDomainRecordsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20010**](inline_response_200_10.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetDomains

> InlineResponse2009 GetDomains(ctx, optional)

List Domains

This is a collection of Domains that you have registered in Linode's DNS Manager.  Linode is not a registrar, and in order for these to work you must own the domains and point your registrar at Linode's nameservers. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetDomainsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetDomainsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse2009**](inline_response_200_9.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ImportDomain

> Domain ImportDomain(ctx, optional)

Import Domain

Imports a domain zone from a remote nameserver. Your nameserver must allow zone transfers (AXFR) from the following IPs:    - 96.126.114.97   - 96.126.114.98   - 2600:3c00::5e   - 2600:3c00::5f 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***ImportDomainOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a ImportDomainOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the Domain to import. | 

### Return type

[**Domain**](Domain.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateDomain

> Domain UpdateDomain(ctx, domainId, domain)

Update Domain

Update information about a Domain in Linode's DNS Manager. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain to access. | 
**domain** | [**Domain**](Domain.md)| The Domain information to update. | 

### Return type

[**Domain**](Domain.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateDomainRecord

> DomainRecord UpdateDomainRecord(ctx, domainId, recordId, domainRecord)

Update Domain Record

Updates a single Record on this Domain. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**domainId** | **int32**| The ID of the Domain whose Record you are accessing. | 
**recordId** | **int32**| The ID of the Record you are accessing. | 
**domainRecord** | [**DomainRecord**](DomainRecord.md)| The values to change. | 

### Return type

[**DomainRecord**](DomainRecord.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

