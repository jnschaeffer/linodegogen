# InvoiceItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Amount** | **float32** | The price, in US dollars, of the Invoice Item. Equal to the unit price multiplied by quantity. | [optional] [readonly] 
**Tax** | **float32** | The amount of tax levied on this Item in US Dollars. | [optional] [readonly] 
**Total** | **float32** | The price of this Item after taxes in US Dollars. | [optional] [readonly] 
**From** | [**time.Time**](time.Time.md) | The date the Invoice Item started, based on month. | [optional] [readonly] 
**Label** | **string** | The Invoice Item&#39;s display label. | [optional] [readonly] 
**Quantity** | **int32** | The quantity of this Item for the specified Invoice. | [optional] [readonly] 
**To** | [**time.Time**](time.Time.md) | The date the Invoice Item ended, based on month. | [optional] [readonly] 
**Type** | **string** | The type of service, ether &#x60;hourly&#x60; or &#x60;misc&#x60;. | [optional] [readonly] 
**UnitPrice** | **string** | The monthly service fee in US Dollars for this Item. | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


