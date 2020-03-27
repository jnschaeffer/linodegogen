# LkeClusterRequestBody

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Label** | **string** | This Kubernetes cluster&#39;s unique label for display purposes only. If no label is provided, one will be assigned automatically. Labels have the following constraints:   * Must start with an alpha character   * Must only consist of alphanumeric characters and dashes (&#x60;-&#x60;)   * Must not contain two dashes in a row  | 
**Region** | **string** | This Kubernetes cluster&#39;s location. | 
**Version** | **string** | The desired Kubernetes version for this Kubernetes cluster in the format of &amp;lt;major&amp;gt;.&amp;lt;minor&amp;gt;, and the latest supported patch version will be deployed.  | 
**Tags** | **[]string** | An array of tags applied to the Kubernetes cluster. Tags are for organizational purposes only.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


