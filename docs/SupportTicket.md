# SupportTicket

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The ID of the Support Ticket.  | [optional] [readonly] 
**Attachments** | **[]string** | A list of filenames representing attached files associated with this Ticket.  | [optional] [readonly] 
**Closed** | Pointer to [**time.Time**](time.Time.md) | The date and time this Ticket was closed.  | [optional] [readonly] 
**Closable** | **bool** | Whether the Support Ticket may be closed.  | [optional] 
**Description** | **string** | The full details of the issue or question.  | [optional] [readonly] 
**Entity** | Pointer to [**SupportTicketEntity**](SupportTicket_entity.md) |  | [optional] 
**GravatarId** | **string** | The Gravatar ID of the User who opened this Ticket.  | [optional] [readonly] 
**Opened** | [**time.Time**](time.Time.md) | The date and time this Ticket was created.  | [optional] [readonly] 
**OpenedBy** | **string** | The User who opened this Ticket.  | [optional] [readonly] 
**Status** | **string** | The current status of this Ticket. | [optional] [readonly] 
**Summary** | **string** | The summary or title for this Ticket.  | [optional] [readonly] 
**Updated** | [**time.Time**](time.Time.md) | The date and time this Ticket was last updated.  | [optional] [readonly] 
**UpdatedBy** | Pointer to **string** | The User who last updated this Ticket.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


