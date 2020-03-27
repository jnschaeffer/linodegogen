# ObjectStorageObject

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Name** | **string** | The name of this object or prefix.  | [optional] 
**Etag** | **string** | An MD-5 hash of the object. &#x60;null&#x60; if this object represents a prefix.  | [optional] 
**LastModified** | [**time.Time**](time.Time.md) | The date and time this object was last modified. &#x60;null&#x60; if this object represents a prefix.  | [optional] 
**Owner** | **string** | The owner of this object, as a UUID. &#x60;null&#x60; if this object represents a prefix.  | [optional] 
**Size** | **int32** | The size of this object, in bytes. &#x60;null&#x60; if this object represents a prefix.  | [optional] 
**NextMarker** | Pointer to **string** | Returns the value you should pass to the &#x60;marker&#x60; query parameter to get the next page of objects. If there is no next page, &#x60;null&#x60; will be returned.  | [optional] 
**IsTruncated** | **bool** | Designates if there is another page of bucket objects. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


