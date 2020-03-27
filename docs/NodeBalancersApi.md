# \NodeBalancersApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateNodeBalancer**](NodeBalancersApi.md#CreateNodeBalancer) | **Post** /nodebalancers | Create NodeBalancer
[**CreateNodeBalancerConfig**](NodeBalancersApi.md#CreateNodeBalancerConfig) | **Post** /nodebalancers/{nodeBalancerId}/configs | Create Config
[**CreateNodeBalancerNode**](NodeBalancersApi.md#CreateNodeBalancerNode) | **Post** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes | Create Node
[**DeleteNodeBalancer**](NodeBalancersApi.md#DeleteNodeBalancer) | **Delete** /nodebalancers/{nodeBalancerId} | Delete NodeBalancer
[**DeleteNodeBalancerConfig**](NodeBalancersApi.md#DeleteNodeBalancerConfig) | **Delete** /nodebalancers/{nodeBalancerId}/configs/{configId} | Delete Config
[**DeleteNodeBalancerConfigNode**](NodeBalancersApi.md#DeleteNodeBalancerConfigNode) | **Delete** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | Delete Node
[**GetNodeBalancer**](NodeBalancersApi.md#GetNodeBalancer) | **Get** /nodebalancers/{nodeBalancerId} | View NodeBalancer
[**GetNodeBalancerConfig**](NodeBalancersApi.md#GetNodeBalancerConfig) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId} | View Config
[**GetNodeBalancerConfigNodes**](NodeBalancersApi.md#GetNodeBalancerConfigNodes) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes | List Nodes
[**GetNodeBalancerConfigs**](NodeBalancersApi.md#GetNodeBalancerConfigs) | **Get** /nodebalancers/{nodeBalancerId}/configs | List Configs
[**GetNodeBalancerNode**](NodeBalancersApi.md#GetNodeBalancerNode) | **Get** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | View Node
[**GetNodeBalancers**](NodeBalancersApi.md#GetNodeBalancers) | **Get** /nodebalancers | List NodeBalancers
[**NodebalancersNodeBalancerIdStatsGet**](NodeBalancersApi.md#NodebalancersNodeBalancerIdStatsGet) | **Get** /nodebalancers/{nodeBalancerId}/stats | View NodeBalancer Statistics
[**RebuildNodeBalancerConfig**](NodeBalancersApi.md#RebuildNodeBalancerConfig) | **Post** /nodebalancers/{nodeBalancerId}/configs/{configId}/rebuild | Rebuild Config
[**UpdateNodeBalancer**](NodeBalancersApi.md#UpdateNodeBalancer) | **Put** /nodebalancers/{nodeBalancerId} | Update NodeBalancer
[**UpdateNodeBalancerConfig**](NodeBalancersApi.md#UpdateNodeBalancerConfig) | **Put** /nodebalancers/{nodeBalancerId}/configs/{configId} | Update Config
[**UpdateNodeBalancerNode**](NodeBalancersApi.md#UpdateNodeBalancerNode) | **Put** /nodebalancers/{nodeBalancerId}/configs/{configId}/nodes/{nodeId} | Update Node



## CreateNodeBalancer

> NodeBalancer CreateNodeBalancer(ctx, uNKNOWNBASETYPE)

Create NodeBalancer

Creates a NodeBalancer in the requested Region. This NodeBalancer will not start serving requests until it is configured. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the NodeBalancer to create. | 

### Return type

[**NodeBalancer**](NodeBalancer.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateNodeBalancerConfig

> NodeBalancerConfig CreateNodeBalancerConfig(ctx, nodeBalancerId, optional)

Create Config

Creates a NodeBalancer Config, which allows the NodeBalancer to accept traffic on a new port. You will need to add NodeBalancer Nodes to the new Config before it can actually serve requests. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
 **optional** | ***CreateNodeBalancerConfigOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateNodeBalancerConfigOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **nodeBalancerConfig** | [**optional.Interface of NodeBalancerConfig**](NodeBalancerConfig.md)| Information about the port to configure. | 

### Return type

[**NodeBalancerConfig**](NodeBalancerConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateNodeBalancerNode

> NodeBalancerNode CreateNodeBalancerNode(ctx, nodeBalancerId, configId, uNKNOWNBASETYPE)

Create Node

Creates a NodeBalancer Node, a backend that can accept traffic for this NodeBalancer Config. Nodes are routed requests on the configured port based on their status. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the NodeBalancer config to access. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the Node to create. | 

### Return type

[**NodeBalancerNode**](NodeBalancerNode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteNodeBalancer

> map[string]interface{} DeleteNodeBalancer(ctx, nodeBalancerId)

Delete NodeBalancer

Deletes a NodeBalancer.  **This is a destructive action and cannot be undone.**  Deleting a NodeBalancer will also delete all associated Configs and Nodes, although the backend servers represented by the Nodes will not be changed or removed. Deleting a NodeBalancer will cause you to lose access to the IP Addresses assigned to this NodeBalancer. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteNodeBalancerConfig

> map[string]interface{} DeleteNodeBalancerConfig(ctx, nodeBalancerId, configId)

Delete Config

Deletes the Config for a port of this NodeBalancer.  **This cannot be undone.**  Once completed, this NodeBalancer will no longer respond to requests on the given port. This also deletes all associated NodeBalancerNodes, but the Linodes they were routing traffic to will be unchanged and will not be removed. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the config to access. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteNodeBalancerConfigNode

> map[string]interface{} DeleteNodeBalancerConfigNode(ctx, nodeBalancerId, configId, nodeId)

Delete Node

Deletes a Node from this Config. This backend will no longer receive traffic for the configured port of this NodeBalancer.  This does not change or remove the Linode whose address was used in the creation of this Node. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the Config to access | 
**nodeId** | **int32**| The ID of the Node to access | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancer

> NodeBalancer GetNodeBalancer(ctx, nodeBalancerId)

View NodeBalancer

Returns a single NodeBalancer you can access. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 

### Return type

[**NodeBalancer**](NodeBalancer.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancerConfig

> NodeBalancerConfig GetNodeBalancerConfig(ctx, nodeBalancerId, configId)

View Config

Returns configuration information for a single port of this NodeBalancer. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the config to access. | 

### Return type

[**NodeBalancerConfig**](NodeBalancerConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancerConfigNodes

> InlineResponse20039 GetNodeBalancerConfigNodes(ctx, nodeBalancerId, configId, optional)

List Nodes

Returns a paginated list of NodeBalancer nodes associated with this Config. These are the backends that will be sent traffic for this port. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the NodeBalancer config to access. | 
 **optional** | ***GetNodeBalancerConfigNodesOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetNodeBalancerConfigNodesOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20039**](inline_response_200_39.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancerConfigs

> InlineResponse20038 GetNodeBalancerConfigs(ctx, nodeBalancerId, optional)

List Configs

Returns a paginated list of NodeBalancer Configs associated with this NodeBalancer. NodeBalancer Configs represent individual ports that this NodeBalancer will accept traffic on, one Config per port.  For example, if you wanted to accept standard HTTP traffic, you would need a Config listening on port 80. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
 **optional** | ***GetNodeBalancerConfigsOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetNodeBalancerConfigsOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20038**](inline_response_200_38.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancerNode

> NodeBalancerNode GetNodeBalancerNode(ctx, nodeBalancerId, configId, nodeId)

View Node

Returns information about a single Node, a backend for this NodeBalancer's configured port. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the Config to access | 
**nodeId** | **int32**| The ID of the Node to access | 

### Return type

[**NodeBalancerNode**](NodeBalancerNode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetNodeBalancers

> InlineResponse20037 GetNodeBalancers(ctx, optional)

List NodeBalancers

Returns a paginated list of NodeBalancers you have access to. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***GetNodeBalancersOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetNodeBalancersOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **page** | **optional.Int32**| The page of a collection to return. | [default to 1]
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

### Return type

[**InlineResponse20037**](inline_response_200_37.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## NodebalancersNodeBalancerIdStatsGet

> NodeBalancerStats NodebalancersNodeBalancerIdStatsGet(ctx, nodeBalancerId)

View NodeBalancer Statistics

Returns detailed statistics about the requested NodeBalancer. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 

### Return type

[**NodeBalancerStats**](NodeBalancerStats.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## RebuildNodeBalancerConfig

> NodeBalancer RebuildNodeBalancerConfig(ctx, nodeBalancerId, configId, uNKNOWNBASETYPE)

Rebuild Config

Rebuilds a NodeBalancer Config and its Nodes that you have permission to modify. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the Config to access. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the NodeBalancer Config to rebuild.  | 

### Return type

[**NodeBalancer**](NodeBalancer.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateNodeBalancer

> NodeBalancer UpdateNodeBalancer(ctx, nodeBalancerId, nodeBalancer)

Update NodeBalancer

Updates information about a NodeBalancer you can access. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**nodeBalancer** | [**NodeBalancer**](NodeBalancer.md)| The information to update. | 

### Return type

[**NodeBalancer**](NodeBalancer.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateNodeBalancerConfig

> NodeBalancerConfig UpdateNodeBalancerConfig(ctx, nodeBalancerId, configId, nodeBalancerConfig)

Update Config

Updates the configuration for a single port on a NodeBalancer. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the config to access. | 
**nodeBalancerConfig** | [**NodeBalancerConfig**](NodeBalancerConfig.md)| The fields to update. | 

### Return type

[**NodeBalancerConfig**](NodeBalancerConfig.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateNodeBalancerNode

> NodeBalancerNode UpdateNodeBalancerNode(ctx, nodeBalancerId, configId, nodeId, nodeBalancerNode)

Update Node

Updates information about a Node, a backend for this NodeBalancer's configured port. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**nodeBalancerId** | **int32**| The ID of the NodeBalancer to access. | 
**configId** | **int32**| The ID of the Config to access | 
**nodeId** | **int32**| The ID of the Node to access | 
**nodeBalancerNode** | [**NodeBalancerNode**](NodeBalancerNode.md)| The fields to update. | 

### Return type

[**NodeBalancerNode**](NodeBalancerNode.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

