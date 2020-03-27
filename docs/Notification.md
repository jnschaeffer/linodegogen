# Notification

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Entity** | [**NotificationEntity**](Notification_entity.md) |  | [optional] 
**Label** | **string** | A short description of this Notification.  | [optional] [readonly] 
**Message** | **string** | A human-readable description of the Notification. | [optional] [readonly] 
**Body** | Pointer to **string** | A full description of this Notification, in markdown format.  Not all Notifications include bodies.  | [optional] [readonly] 
**Type** | **string** | The type of Notification this is. | [optional] [readonly] 
**Severity** | **string** | The severity of this Notification.  This field can be used to decide how prominently to display the Notification, what color to make the display text, etc.  | [optional] [readonly] 
**When** | [**time.Time**](time.Time.md) | If this Notification is of an Event that will happen at a fixed, future time, this is when the named action will be taken. For example, if a Linode is to be migrated in response to a Security Advisory, this field will contain the approximate time the Linode will be taken offline for migration.  | [optional] [readonly] 
**Until** | [**time.Time**](time.Time.md) | If this Notification has a duration, this will be the ending time for the Event/action. For example, if there is scheduled maintenance for one of our systems, &#x60;until&#x60; would be set to the end of the maintenance window.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


