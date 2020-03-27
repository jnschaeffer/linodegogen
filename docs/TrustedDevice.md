# TrustedDevice

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The unique ID for this TrustedDevice | [optional] [readonly] 
**Created** | [**time.Time**](time.Time.md) | When this Remember Me session was started.  This corresponds to the time of login with the \&quot;Remember Me\&quot; box checked.  | [optional] [readonly] 
**Expiry** | [**time.Time**](time.Time.md) | When this TrustedDevice session expires.  Sessions typically last 30 days.  | [optional] [readonly] 
**UserAgent** | **string** | The User Agent of the browser that created this TrustedDevice session.  | [optional] [readonly] 
**LastAuthenticated** | [**time.Time**](time.Time.md) | The last time this TrustedDevice was successfully used to authenticate to &lt;a target&#x3D;\&quot;_top\&quot; href&#x3D;\&quot;https://login.linode.com\&quot;&gt;login.linode.com&lt;/a&gt;.  | [optional] [readonly] 
**LastRemoteAddr** | **string** | The last IP Address to successfully authenticate with this TrustedDevice.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


