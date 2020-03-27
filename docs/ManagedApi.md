# \ManagedApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateManagedContact**](ManagedApi.md#CreateManagedContact) | **Post** /managed/contacts | Create Managed Contact
[**CreateManagedCredential**](ManagedApi.md#CreateManagedCredential) | **Post** /managed/credentials | Create Managed Credential
[**CreateManagedService**](ManagedApi.md#CreateManagedService) | **Post** /managed/services | Create Managed Service
[**DeleteManagedContact**](ManagedApi.md#DeleteManagedContact) | **Delete** /managed/contacts/{contactId} | Delete Managed Contact
[**DeleteManagedCredential**](ManagedApi.md#DeleteManagedCredential) | **Post** /managed/credentials/{credentialId}/revoke | Delete Managed Credential
[**DeleteManagedService**](ManagedApi.md#DeleteManagedService) | **Delete** /managed/services/{serviceId} | Delete Managed Service
[**DisableManagedService**](ManagedApi.md#DisableManagedService) | **Post** /managed/services/{serviceId}/disable | Disable Managed Service
[**EnableManagedService**](ManagedApi.md#EnableManagedService) | **Post** /managed/services/{serviceId}/enable | Enable Managed Service
[**GetManagedContact**](ManagedApi.md#GetManagedContact) | **Get** /managed/contacts/{contactId} | View Managed Contact
[**GetManagedContacts**](ManagedApi.md#GetManagedContacts) | **Get** /managed/contacts | List Managed Contacts
[**GetManagedCredential**](ManagedApi.md#GetManagedCredential) | **Get** /managed/credentials/{credentialId} | View Managed Credential
[**GetManagedCredentials**](ManagedApi.md#GetManagedCredentials) | **Get** /managed/credentials | List Managed Credentials
[**GetManagedIssue**](ManagedApi.md#GetManagedIssue) | **Get** /managed/issues/{issueId} | View Managed Issue
[**GetManagedIssues**](ManagedApi.md#GetManagedIssues) | **Get** /managed/issues | List Managed Issues
[**GetManagedLinodeSetting**](ManagedApi.md#GetManagedLinodeSetting) | **Get** /managed/linode-settings/{linodeId} | View Linode&#39;s Managed Settings
[**GetManagedLinodeSettings**](ManagedApi.md#GetManagedLinodeSettings) | **Get** /managed/linode-settings | List Managed Linode Settings
[**GetManagedService**](ManagedApi.md#GetManagedService) | **Get** /managed/services/{serviceId} | View Managed Service
[**GetManagedServices**](ManagedApi.md#GetManagedServices) | **Get** /managed/services | List Managed Services
[**GetManagedStats**](ManagedApi.md#GetManagedStats) | **Get** /managed/stats | List Managed Stats
[**UpdateManagedContact**](ManagedApi.md#UpdateManagedContact) | **Put** /managed/contacts/{contactId} | Update Managed Contact
[**UpdateManagedCredential**](ManagedApi.md#UpdateManagedCredential) | **Put** /managed/credentials/{credentialId} | Update Managed Credential
[**UpdateManagedCredentialUsernamePassword**](ManagedApi.md#UpdateManagedCredentialUsernamePassword) | **Post** /managed/credentials/{credentialId}/update | Update Managed Credential Username and Password
[**UpdateManagedLinodeSetting**](ManagedApi.md#UpdateManagedLinodeSetting) | **Put** /managed/linode-settings/{linodeId} | Update Linode&#39;s Managed Settings
[**UpdateManagedService**](ManagedApi.md#UpdateManagedService) | **Put** /managed/services/{serviceId} | Update Managed Service
[**ViewManagedSSHKey**](ManagedApi.md#ViewManagedSSHKey) | **Get** /managed/credentials/sshkey | View Managed SSH Key



## CreateManagedContact

> ManagedContact CreateManagedContact(ctx, optional)

Create Managed Contact

Creates a Managed Contact.  A Managed Contact is someone Linode special forces can contact in the course of attempting to resolve an issue with a Managed Service. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateManagedContactOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateManagedContactOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **managedContact** | [**optional.Interface of ManagedContact**](ManagedContact.md)| Information about the contact to create. | 

### Return type

[**ManagedContact**](ManagedContact.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateManagedCredential

> ManagedCredential CreateManagedCredential(ctx, optional)

Create Managed Credential

Creates a Managed Credential. A Managed Credential is stored securely to allow Linode special forces to access your Managed Services and resolve issues. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateManagedCredentialOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateManagedCredentialOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the Credential to create. | 

### Return type

[**ManagedCredential**](ManagedCredential.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateManagedService

> ManagedService CreateManagedService(ctx, optional)

Create Managed Service

Creates a Managed Service. Linode Managed will begin monitoring this service and reporting and attempting to resolve any Issues. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateManagedServiceOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateManagedServiceOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the service to monitor. | 

### Return type

[**ManagedService**](ManagedService.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteManagedContact

> map[string]interface{} DeleteManagedContact(ctx, contactId)

Delete Managed Contact

Deletes a Managed Contact. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**contactId** | **int32**| The ID of the contact to access. | 

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


## DeleteManagedCredential

> map[string]interface{} DeleteManagedCredential(ctx, credentialId)

Delete Managed Credential

Deletes a Managed Credential.  Linode special forces will no longer have access to this Credential when attempting to resolve issues. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**credentialId** | **int32**| The ID of the Credential to access. | 

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


## DeleteManagedService

> map[string]interface{} DeleteManagedService(ctx, serviceId)

Delete Managed Service

Deletes a Managed Service.  This service will no longer be monitored by Linode Managed. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**serviceId** | **int32**| The ID of the Managed Service to access. | 

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


## DisableManagedService

> ManagedService DisableManagedService(ctx, serviceId)

Disable Managed Service

Temporarily disables monitoring of a Managed Service. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**serviceId** | **int32**| The ID of the Managed Service to disable. | 

### Return type

[**ManagedService**](ManagedService.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## EnableManagedService

> ManagedService EnableManagedService(ctx, serviceId)

Enable Managed Service

Enables monitoring of a Managed Service. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**serviceId** | **int32**| The ID of the Managed Service to enable. | 

### Return type

[**ManagedService**](ManagedService.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedContact

> ManagedContact GetManagedContact(ctx, contactId)

View Managed Contact

Returns a single Managed Contact. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**contactId** | **int32**| The ID of the contact to access. | 

### Return type

[**ManagedContact**](ManagedContact.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedContacts

> InlineResponse20027 GetManagedContacts(ctx, optional)

List Managed Contacts

Returns a paginated list of Managed Contacts on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetManagedContactsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetManagedContactsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20027**](inline_response_200_27.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedCredential

> ManagedCredential GetManagedCredential(ctx, credentialId)

View Managed Credential

Returns a single Managed Credential. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**credentialId** | **int32**| The ID of the Credential to access. | 

### Return type

[**ManagedCredential**](ManagedCredential.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedCredentials

> InlineResponse20028 GetManagedCredentials(ctx, optional)

List Managed Credentials

Returns a paginated list of Managed Credentials on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetManagedCredentialsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetManagedCredentialsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20028**](inline_response_200_28.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedIssue

> ManagedIssue GetManagedIssue(ctx, issueId)

View Managed Issue

Returns a single Issue that is impacting or did impact one of your Managed Services. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**issueId** | **int32**| The Issue to look up. | 

### Return type

[**ManagedIssue**](ManagedIssue.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedIssues

> InlineResponse20030 GetManagedIssues(ctx, optional)

List Managed Issues

Returns a paginated list of recent and ongoing issues detected on your Managed Services. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetManagedIssuesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetManagedIssuesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20030**](inline_response_200_30.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedLinodeSetting

> ManagedLinodeSettings GetManagedLinodeSetting(ctx, linodeId)

View Linode's Managed Settings

Returns a single Linode's Managed settings. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The Linode ID whose settings we are accessing. | 

### Return type

[**ManagedLinodeSettings**](ManagedLinodeSettings.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedLinodeSettings

> InlineResponse20031 GetManagedLinodeSettings(ctx, optional)

List Managed Linode Settings

Returns a paginated list of Managed Settings for your Linodes. There will be one entry per Linode on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetManagedLinodeSettingsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetManagedLinodeSettingsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20031**](inline_response_200_31.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedService

> ManagedService GetManagedService(ctx, serviceId)

View Managed Service

Returns information about a single Managed Service on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**serviceId** | **int32**| The ID of the Managed Service to access. | 

### Return type

[**ManagedService**](ManagedService.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedServices

> InlineResponse20032 GetManagedServices(ctx, )

List Managed Services

Returns a paginated list of Managed Services on your Account. These are the services Linode Managed is monitoring and will report and attempt to resolve issues with. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20032**](inline_response_200_32.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetManagedStats

> InlineResponse20033 GetManagedStats(ctx, )

List Managed Stats

Returns a list of Managed Stats on your Account in the form of x and y data points. You can use these data points to plot your own graph visualizations. These stats reflect the last 24 hours of combined usage across all managed Linodes on your account giving you a high-level snapshot of data for the following:   * cpu * disk * swap * network in * network out 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20033**](inline_response_200_33.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateManagedContact

> ManagedContact UpdateManagedContact(ctx, contactId, managedContact)

Update Managed Contact

Updates information about a Managed Contact. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**contactId** | **int32**| The ID of the contact to access. | 
**managedContact** | [**ManagedContact**](ManagedContact.md)| The fields to update. | 

### Return type

[**ManagedContact**](ManagedContact.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateManagedCredential

> ManagedCredential UpdateManagedCredential(ctx, credentialId, managedCredential)

Update Managed Credential

Updates the label of a Managed Credential. This endpoint does not update the username and password for a Managed Credential. To do this, use the Update Managed Credential Username and Password ([POST /managed/credentials/{credentialId}/update](https://developers.linode.com/api/docs/v4#operation/updateManagedCredentialUsernamePassword)) endpoint instead. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**credentialId** | **int32**| The ID of the Credential to access. | 
**managedCredential** | [**ManagedCredential**](ManagedCredential.md)| The fields to update. | 

### Return type

[**ManagedCredential**](ManagedCredential.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateManagedCredentialUsernamePassword

> map[string]interface{} UpdateManagedCredentialUsernamePassword(ctx, credentialId, optional)

Update Managed Credential Username and Password

Updates the username and password for a Managed Credential. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**credentialId** | **int32**| The ID of the Credential to update. | 
 **optional** | ***UpdateManagedCredentialUsernamePasswordOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a UpdateManagedCredentialUsernamePasswordOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The new username and password to assign to the Managed Credential.  | 

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


## UpdateManagedLinodeSetting

> ManagedLinodeSettings UpdateManagedLinodeSetting(ctx, linodeId, managedLinodeSettings)

Update Linode's Managed Settings

Updates a single Linode's Managed settings. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**linodeId** | **int32**| The Linode ID whose settings we are accessing. | 
**managedLinodeSettings** | [**ManagedLinodeSettings**](ManagedLinodeSettings.md)| The settings to update. | 

### Return type

[**ManagedLinodeSettings**](ManagedLinodeSettings.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateManagedService

> ManagedService UpdateManagedService(ctx, serviceId, managedService)

Update Managed Service

Updates information about a Managed Service. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**serviceId** | **int32**| The ID of the Managed Service to access. | 
**managedService** | [**ManagedService**](ManagedService.md)| The fields to update. | 

### Return type

[**ManagedService**](ManagedService.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ViewManagedSSHKey

> InlineResponse20029 ViewManagedSSHKey(ctx, )

View Managed SSH Key

Returns the unique SSH public key assigned to your Linode account's Managed service. If you [add this public key](https://linode.com/docs/platform/linode-managed/#adding-the-public-key) to a Linode on your account, Linode special forces will be able to log in to the Linode with this key when attempting to resolve issues. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20029**](inline_response_200_29.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

