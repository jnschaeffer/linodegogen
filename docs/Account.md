# Account

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ActivePromotions** | [**[]AccountActivePromotions**](Account_active_promotions.md) |  | [optional] 
**ActiveSince** | [**time.Time**](time.Time.md) | The datetime of when the account was activated. | [optional] [readonly] 
**Address1** | **string** | First line of this Account&#39;s billing address. | [optional] 
**Address2** | **string** | Second line of this Account&#39;s billing address. | [optional] 
**Balance** | **float32** | This Account&#39;s balance, in US dollars. | [optional] [readonly] 
**BalanceUninvoiced** | **float32** | This Account&#39;s current estimated invoice in US dollars. This is not your final invoice balance. Bandwidth charges are not included in the estimate.  | [optional] [readonly] 
**Capabilities** | **[]string** | A list of capabilities your account supports.  | [optional] [readonly] 
**City** | **string** | The city for this Account&#39;s billing address. | [optional] 
**CreditCard** | [**AccountCreditCard**](Account_credit_card.md) |  | [optional] 
**Company** | **string** | The company name associated with this Account. | [optional] 
**Country** | **string** | The two-letter country code of this Account&#39;s billing address.  | [optional] 
**Email** | **string** | The email address of the person associated with this Account. | [optional] 
**FirstName** | **string** | The first name of the person associated with this Account. | [optional] 
**LastName** | **string** | The last name of the person associated with this Account. | [optional] 
**Phone** | **string** | The phone number associated with this Account. | [optional] 
**State** | **string** | If billing address is in the United States, this is the State portion of the Account&#39;s billing address. If the address is outside the US, this is the Province associated with the Account&#39;s billing address.  | [optional] 
**TaxId** | **string** | The tax identification number associated with this Account, for tax calculations in some countries. If you do not live in a country that collects tax, this should be &#x60;null&#x60;.  | [optional] 
**Euuid** | **string** | An external unique identifier for this account.  | [optional] [readonly] 
**Zip** | **string** | The zip code of this Account&#39;s billing address. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


