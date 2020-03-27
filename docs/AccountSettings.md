# AccountSettings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Managed** | **bool** | Our 24/7 incident response service. This robust, multi-homed monitoring system distributes monitoring checks to ensure that your servers remain online and available at all times. Linode Managed can monitor any service or software stack reachable over TCP or HTTP. Once you add a service to Linode Managed, we&#39;ll monitor it for connectivity, response, and total request time.  | [optional] [readonly] 
**LongviewSubscription** | **string** | The Longview Pro tier you are currently subscribed to. The value must a [Longview Subscription](/api/v4/longview-subscriptions) ID or &#x60;null&#x60;.  | [optional] 
**NetworkHelper** | **bool** | Enables network helper across all users by default for new Linodes and Linode Configs.  | [optional] 
**BackupsEnabled** | **bool** | Account-wide backups default.  If &#x60;true&#x60;, all Linodes created will automatically be enrolled in the Backups service.  If &#x60;false&#x60;, Linodes will not be enrolled by default, but may still be enrolled on creation or later.  | [optional] 
**ObjectStorage** | **string** | A string describing the status of this account&#39;s Object Storage service enrollment.  | [optional] [readonly] [default to OBJECT_STORAGE_DISABLED]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


