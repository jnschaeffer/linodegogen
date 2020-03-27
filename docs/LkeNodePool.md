# LkeNodePool

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This Node Pool&#39;s unique ID.  | [optional] 
**Nodes** | [**[]LkeNodeStatus**](LKENodeStatus.md) | Status information for the Nodes which are members of this Node Pool. If a Linode has not been provisioned for a given Node slot, the instance_id will be returned as null.  | [optional] 
**Type** | **string** | A Linode Type for all of the nodes in the Node Pool. | [optional] 
**Count** | **int32** | The number of nodes in the Node Pool. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


