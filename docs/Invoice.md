# Invoice

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | The Invoice&#39;s unique ID. | [optional] [readonly] 
**Date** | [**time.Time**](time.Time.md) | When this Invoice was generated. | [optional] [readonly] 
**Label** | **string** | The Invoice&#39;s display label. | [optional] [readonly] 
**Subtotal** | **float32** | The amount of the Invoice before taxes in US Dollars. | [optional] [readonly] 
**Tax** | **float32** | The amount of tax levied on the Invoice in US Dollars. | [optional] [readonly] 
**Total** | **float32** | The amount of the Invoice after taxes in US Dollars. | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


