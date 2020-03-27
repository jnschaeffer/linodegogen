# AuthorizedApp

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This authorization&#39;s ID, used for revoking access.  | [optional] [readonly] 
**Label** | **string** | The name of the application you&#39;ve authorized.  | [optional] [readonly] 
**ThumbnailUrl** | **string** | The URL at which this app&#39;s thumbnail may be accessed.  | [optional] [readonly] 
**Scopes** | **string** | The OAuth scopes this app was authorized with.  This defines what parts of your Account the app is allowed to access.  | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this app was authorized. | [optional] [readonly] 
**Expiry** | [**time.Time**](time.Time.md) | When this app&#39;s access token expires.  Please note that apps may still have active refresh tokens after this time passes.  | [optional] [readonly] 
**Website** | **string** | The website where you can get more information about this app.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


