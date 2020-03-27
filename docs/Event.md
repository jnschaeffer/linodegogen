# Event

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The unique ID of this Event. | [optional] [readonly] 
**Action** | **string** | The action that caused this Event. New actions may be added in the future.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this Event was created. | [optional] [readonly] 
**Duration** | **float32** | The total duration in seconds that it takes for the Event to complete.  | [optional] [readonly] 
**Entity** | [**EventEntity**](Event_entity.md) |  | [optional] 
**SecondaryEntity** | [**EventSecondaryEntity**](Event_secondary_entity.md) |  | [optional] 
**PercentComplete** | **int32** | A percentage estimating the amount of time remaining for an Event. Returns &#x60;null&#x60; for notification events.  | [optional] [readonly] 
**Rate** | **string** | The rate of completion of the Event. Only some Events will return rate; for example, migration and resize Events.  | [optional] [readonly] 
**Read** | **bool** | If this Event has been read. | [optional] [readonly] 
**Seen** | **bool** | If this Event has been seen. | [optional] [readonly] 
**Status** | **string** | The current status of this Event. | [optional] [readonly] 
**TimeRemaining** | Pointer to **string** | The estimated time remaining until the completion of this Event. This value is only returned for some in-progress migration events. For all other in-progress events, the &#x60;percent_complete&#x60; attribute will indicate about how much more work is to be done.  | [optional] [readonly] 
**Username** | **string** | The username of the User who caused the Event.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


