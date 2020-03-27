# \LinodeKubernetesEngineLKEApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CreateLKECluster**](LinodeKubernetesEngineLKEApi.md#CreateLKECluster) | **Post** /lke/clusters | Create Kubernetes Cluster
[**DeleteLKECluster**](LinodeKubernetesEngineLKEApi.md#DeleteLKECluster) | **Delete** /lke/clusters/{clusterId} | Delete Kubernetes Cluster
[**DeleteLKENodePool**](LinodeKubernetesEngineLKEApi.md#DeleteLKENodePool) | **Delete** /lke/clusters/{clusterId}/pools/{poolId} | Delete Node Pool
[**GetLKECluster**](LinodeKubernetesEngineLKEApi.md#GetLKECluster) | **Get** /lke/clusters/{clusterId} | View Kubernetes Cluster
[**GetLKEClusterAPIEndpoint**](LinodeKubernetesEngineLKEApi.md#GetLKEClusterAPIEndpoint) | **Get** /lke/clusters/{clusterId}/api-endpoint | View Kubernetes API Endpoint
[**GetLKEClusterKubeconfig**](LinodeKubernetesEngineLKEApi.md#GetLKEClusterKubeconfig) | **Get** /lke/clusters/{clusterId}/kubeconfig | View Kubeconfig
[**GetLKEClusterPools**](LinodeKubernetesEngineLKEApi.md#GetLKEClusterPools) | **Get** /lke/clusters/{clusterId}/pools | List Node Pools
[**GetLKEClusters**](LinodeKubernetesEngineLKEApi.md#GetLKEClusters) | **Get** /lke/clusters | List Kubernetes Clusters
[**GetLKENodePool**](LinodeKubernetesEngineLKEApi.md#GetLKENodePool) | **Get** /lke/clusters/{clusterId}/pools/{poolId} | View Node Pool
[**GetLKEVersion**](LinodeKubernetesEngineLKEApi.md#GetLKEVersion) | **Get** /lke/versions/{version} | View Kubernetes Version
[**GetLKEVersions**](LinodeKubernetesEngineLKEApi.md#GetLKEVersions) | **Get** /lke/versions | List Kubernetes Versions
[**PostLKEClusterPools**](LinodeKubernetesEngineLKEApi.md#PostLKEClusterPools) | **Post** /lke/clusters/{clusterId}/pools | Create Node Pool
[**PutLKECluster**](LinodeKubernetesEngineLKEApi.md#PutLKECluster) | **Put** /lke/clusters/{clusterId} | Update Kubernetes Cluster
[**PutLKENodePool**](LinodeKubernetesEngineLKEApi.md#PutLKENodePool) | **Put** /lke/clusters/{clusterId}/pools/{poolId} | Update Node Pool



## CreateLKECluster

> LkeCluster CreateLKECluster(ctx, optional)

Create Kubernetes Cluster

Creates a Kubernetes cluster. The Kubernetes cluster will be created asynchronously. You can use the events system to determine when the Kubernetes cluster is ready to use.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateLKEClusterOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateLKEClusterOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Configuration for the Kubernetes cluster | 

### Return type

[**LkeCluster**](LKECluster.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteLKECluster

> map[string]interface{} DeleteLKECluster(ctx, clusterId)

Delete Kubernetes Cluster

Deletes a Cluster you have permission to `read_write`.  **Deleting a Cluster is a destructive action and cannot be undone.**  Deleting a Cluster:   - Deletes all Linodes in all pools within this Kubernetes cluster   - Deletes all supporting Kubernetes services for this Kubernetes     cluster (API server, etcd, etc)   - Deletes all NodeBalancers created by this Kubernetes cluster   - Does not delete any of the volumes created by this Kubernetes     cluster   **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 

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


## DeleteLKENodePool

> map[string]interface{} DeleteLKENodePool(ctx, clusterId, poolId)

Delete Node Pool

Delete a specific Node Pool from a Kubernetes cluster.  **Deleting a Node Pool is a destructive action and cannot be undone.**  Deleting a Node Pool will delete all Linodes within that Pool.   **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 
**poolId** | **int32**| ID of the Pool to look up | 

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


## GetLKECluster

> LkeCluster GetLKECluster(ctx, clusterId)

View Kubernetes Cluster

Get a specific Cluster by ID.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 

### Return type

[**LkeCluster**](LKECluster.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEClusterAPIEndpoint

> InlineResponse20022 GetLKEClusterAPIEndpoint(ctx, clusterId)

View Kubernetes API Endpoint

Get the Kubernetes API server endpoint for this cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 

### Return type

[**InlineResponse20022**](inline_response_200_22.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEClusterKubeconfig

> InlineResponse20023 GetLKEClusterKubeconfig(ctx, clusterId)

View Kubeconfig

Get the Kubeconfig file for a Cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 

### Return type

[**InlineResponse20023**](inline_response_200_23.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEClusterPools

> InlineResponse20021 GetLKEClusterPools(ctx, clusterId)

List Node Pools

Returns all active Node Pools on a Kubernetes cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 

### Return type

[**InlineResponse20021**](inline_response_200_21.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEClusters

> InlineResponse20020 GetLKEClusters(ctx, )

List Kubernetes Clusters

Lists current Kubernetes clusters available on your account.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20020**](inline_response_200_20.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKENodePool

> LkeNodePool GetLKENodePool(ctx, clusterId, poolId)

View Node Pool

Get a specific Node Pool by ID.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 
**poolId** | **int32**| ID of the Pool to look up | 

### Return type

[**LkeNodePool**](LKENodePool.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEVersion

> LkeVersion GetLKEVersion(ctx, version)

View Kubernetes Version

View a Kubernetes version available for deployment to a Kubernetes cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**version** | **string**| The LKE version to view. | 

### Return type

[**LkeVersion**](LKEVersion.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetLKEVersions

> InlineResponse20024 GetLKEVersions(ctx, )

List Kubernetes Versions

List the Kubernetes versions available for deployment to a Kubernetes cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20024**](inline_response_200_24.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## PostLKEClusterPools

> LkeNodePool PostLKEClusterPools(ctx, clusterId, uNKNOWNBASETYPE)

Create Node Pool

Creates a new Node Pool for the designated Kubernetes cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 
**uNKNOWNBASETYPE** | [**UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Configuration for the Node Pool | 

### Return type

[**LkeNodePool**](LKENodePool.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## PutLKECluster

> LkeCluster PutLKECluster(ctx, clusterId, optional)

Update Kubernetes Cluster

Updates a Kubernetes cluster.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 
 **optional** | ***PutLKEClusterOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a PutLKEClusterOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The fields to update the Kubernetes cluster. | 

### Return type

[**LkeCluster**](LKECluster.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## PutLKENodePool

> LkeNodePool PutLKENodePool(ctx, clusterId, poolId, optional)

Update Node Pool

Updates a Node Pool. When a Node Pool's count are changed, the nodes in that pool will be replaced in a rolling fashion.  **Beta**: This endpoint is in private beta. Please make sure to prepend all requests with `/v4beta` instead of `/v4`, and be aware that this endpoint may receive breaking updates in the future. This notice will be removed when this endpoint is out of beta. Sign up for the beta [here](https://welcome.linode.com/lkebeta/). 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **int32**| ID of the Kubernetes cluster to look up. | 
**poolId** | **int32**| ID of the Pool to look up | 
 **optional** | ***PutLKENodePoolOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a PutLKENodePoolOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The fields to update | 

### Return type

[**LkeNodePool**](LKENodePool.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

