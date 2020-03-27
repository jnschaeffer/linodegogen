# \SupportApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CloseTicket**](SupportApi.md#CloseTicket) | **Post** /support/tickets/{ticketId}/close | Close Support Ticket
[**CreateTicket**](SupportApi.md#CreateTicket) | **Post** /support/tickets | Open Support Ticket
[**CreateTicketAttachment**](SupportApi.md#CreateTicketAttachment) | **Post** /support/tickets/{ticketId}/attachments | Create Ticket Attachment
[**CreateTicketReply**](SupportApi.md#CreateTicketReply) | **Post** /support/tickets/{ticketId}/replies | Create Reply
[**GetTicket**](SupportApi.md#GetTicket) | **Get** /support/tickets/{ticketId} | View Support Ticket
[**GetTicketReplies**](SupportApi.md#GetTicketReplies) | **Get** /support/tickets/{ticketId}/replies | List Replies
[**GetTickets**](SupportApi.md#GetTickets) | **Get** /support/tickets | List Support Tickets



## CloseTicket

> map[string]interface{} CloseTicket(ctx, ticketId)

Close Support Ticket

Closes a Support Ticket you have access to modify. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**ticketId** | **int32**| The ID of the Support Ticket. | 

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


## CreateTicket

> SupportTicket CreateTicket(ctx, optional)

Open Support Ticket

Open a Support Ticket. Only one of the ID attributes (`linode_id`, `domain_id`, etc.) can be set on a single Support Ticket. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateTicketOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateTicketOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **supportTicketRequest** | [**optional.Interface of SupportTicketRequest**](SupportTicketRequest.md)| Open a Support Ticket. | 

### Return type

[**SupportTicket**](SupportTicket.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateTicketAttachment

> map[string]interface{} CreateTicketAttachment(ctx, ticketId, file)

Create Ticket Attachment

Adds a file attachment to an existing Support Ticket on your Account. File attachments are used to assist our Support team in resolving your Ticket. Examples of attachments are screen shots and text files that provide additional information. Note: Accepted file extensions include: .gif, .jpg, .jpeg, .pjpg, .pjpeg, .tif, .tiff, .png, .pdf, or .txt. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**ticketId** | **int32**| The ID of the Support Ticket. | 
**file** | **string**| The local, absolute path to the file you want to attach to your Support Ticket.  | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateTicketReply

> SupportTicketReply CreateTicketReply(ctx, ticketId, uNKNOWNBASETYPE)

Create Reply

Adds a reply to an existing Support Ticket. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**ticketId** | **int32**| The ID of the Support Ticket. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Add a reply. | 

### Return type

[**SupportTicketReply**](SupportTicketReply.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetTicket

> SupportTicket GetTicket(ctx, ticketId)

View Support Ticket

Returns a Support Ticket under your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**ticketId** | **int32**| The ID of the Support Ticket. | 

### Return type

[**SupportTicket**](SupportTicket.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetTicketReplies

> InlineResponse20049 GetTicketReplies(ctx, ticketId, optional)

List Replies

Returns a collection of replies to a Support Ticket on your Account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**ticketId** | **int32**| The ID of the Support Ticket. | 
 **optional** | ***GetTicketRepliesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetTicketRepliesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20049**](inline_response_200_49.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetTickets

> InlineResponse20048 GetTickets(ctx, optional)

List Support Tickets

Returns a collection of Support Tickets on your Account. Support Tickets can be both tickets you open with Linode for support, as well as tickets generated by Linode regarding your Account. This collection includes all Support Tickets generated on your Account, with open tickets returned first. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetTicketsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetTicketsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20048**](inline_response_200_48.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

