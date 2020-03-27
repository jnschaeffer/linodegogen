# ImagePrivate

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | The unique ID of this Image. | [optional] [readonly] 
**Label** | **string** | A short description of the Image. Labels cannot contain special characters.  | [optional] 
**Created** | [**time.Time**](time.Time.md) | When this Image was created. | [optional] [readonly] 
**CreatedBy** | **string** | The name of the User who created this Image.  | [optional] [readonly] 
**Deprecated** | **bool** | Whether or not this Image is deprecated. Will only be True for deprecated public Images.  | [optional] [readonly] 
**Description** | **string** | A detailed description of this Image. | [optional] 
**IsPublic** | **bool** | True if the Image is public. | [optional] [readonly] 
**Size** | **int32** | The minimum size this Image needs to deploy. Size is in MB.  | [optional] [readonly] 
**Type** | **string** | How the Image was created. \&quot;Manual\&quot; Images can be created at any time. \&quot;Automatic\&quot; images are created automatically from a deleted Linode.  | [optional] [readonly] 
**Expiry** | [**time.Time**](time.Time.md) | Only Images created automatically (from a deleted Linode; type&#x3D;automatic) will expire.  | [optional] [readonly] 
**Eol** | [**time.Time**](time.Time.md) | The date of the image&#39;s planned end of life. Some images, like custom private images, will not have an end of life date. In that case this field will be &#x60;None&#x60;.  | [optional] [readonly] 
**Vendor** | Pointer to **string** | The upstream distribution vendor. &#x60;None&#x60; for private Images.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


