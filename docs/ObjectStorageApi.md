# \ObjectStorageApi

All URIs are relative to *https://api.linode.com/v4*

Method | HTTP request | Description
------------- | ------------- | -------------
[**CancelObjectStorage**](ObjectStorageApi.md#CancelObjectStorage) | **Post** /object-storage/cancel | Cancel Object Storage
[**CreateObjectStorageBucket**](ObjectStorageApi.md#CreateObjectStorageBucket) | **Post** /object-storage/buckets | Create Object Storage Bucket
[**CreateObjectStorageKeys**](ObjectStorageApi.md#CreateObjectStorageKeys) | **Post** /object-storage/keys | Create an Object Storage Key
[**CreateObjectStorageObjectURL**](ObjectStorageApi.md#CreateObjectStorageObjectURL) | **Post** /object-storage/buckets/{clusterId}/{bucket}/object-url | Create Object Storage Object URL
[**DeleteObjectStorageBucket**](ObjectStorageApi.md#DeleteObjectStorageBucket) | **Delete** /object-storage/buckets/{clusterId}/{bucket} | Remove Object Storage Bucket
[**DeleteObjectStorageKey**](ObjectStorageApi.md#DeleteObjectStorageKey) | **Delete** /object-storage/keys/{keyId} | Revoke Object Storage Key
[**GetObjectStorageBucket**](ObjectStorageApi.md#GetObjectStorageBucket) | **Get** /object-storage/buckets/{clusterId}/{bucket} | View Object Storage Bucket
[**GetObjectStorageBucketContent**](ObjectStorageApi.md#GetObjectStorageBucketContent) | **Get** /object-storage/buckets/{clusterId}/{bucket}/object-list | List Object Storage Bucket Contents
[**GetObjectStorageBucketinCluster**](ObjectStorageApi.md#GetObjectStorageBucketinCluster) | **Get** /object-storage/buckets/{clusterId} | List Object Storage Buckets in Cluster
[**GetObjectStorageBuckets**](ObjectStorageApi.md#GetObjectStorageBuckets) | **Get** /object-storage/buckets | List Object Storage Buckets
[**GetObjectStorageCluster**](ObjectStorageApi.md#GetObjectStorageCluster) | **Get** /object-storage/clusters/{clusterId} | View Cluster
[**GetObjectStorageClusters**](ObjectStorageApi.md#GetObjectStorageClusters) | **Get** /object-storage/clusters | List Clusters
[**GetObjectStorageKey**](ObjectStorageApi.md#GetObjectStorageKey) | **Get** /object-storage/keys/{keyId} | View Object Storage Key
[**GetObjectStorageKeys**](ObjectStorageApi.md#GetObjectStorageKeys) | **Get** /object-storage/keys | List Object Storage Keys
[**ModifyObjectStorageBucketAccess**](ObjectStorageApi.md#ModifyObjectStorageBucketAccess) | **Post** /object-storage/buckets/{clusterId}/{bucket}/access | Modify Object Storage Bucket Access
[**UpdateObjectStorageKey**](ObjectStorageApi.md#UpdateObjectStorageKey) | **Put** /object-storage/keys/{keyId} | Update an Object Storage Key



## CancelObjectStorage

> map[string]interface{} CancelObjectStorage(ctx, )

Cancel Object Storage

Cancel Object Storage on an Account. All buckets on the Account must be empty before Object Storage can be cancelled:  - To delete a smaller number of objects, review the instructions in our [How to Use Object Storage](https://www.linode.com/docs/platform/object-storage/how-to-use-object-storage/) guide. - To delete large amounts of objects, consult our guide on [Lifecycle Policies](https://www.linode.com/docs/platform/object-storage/lifecycle-policies/). 

### Required Parameters

This endpoint does not need any parameter.

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


## CreateObjectStorageBucket

> ObjectStorageBucket CreateObjectStorageBucket(ctx, optional)

Create Object Storage Bucket

Creates an Object Storage Bucket in the cluster specified. If the bucket already exists and is owned by you, this endpoint will return a `200` response with that bucket as if it had just been created.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/bucketops/#put-bucket) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateObjectStorageBucketOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateObjectStorageBucketOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inlineObject9** | [**optional.Interface of InlineObject9**](InlineObject9.md)|  | 

### Return type

[**ObjectStorageBucket**](ObjectStorageBucket.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateObjectStorageKeys

> ObjectStorageKey CreateObjectStorageKeys(ctx, optional)

Create an Object Storage Key

Provisions a new Object Storage Key on your account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
 **optional** | ***CreateObjectStorageKeysOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateObjectStorageKeysOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **inlineObject10** | [**optional.Interface of InlineObject10**](InlineObject10.md)|  | 

### Return type

[**ObjectStorageKey**](ObjectStorageKey.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## CreateObjectStorageObjectURL

> map[string]interface{} CreateObjectStorageObjectURL(ctx, clusterId, bucket, optional)

Create Object Storage Object URL

Creates a pre-signed URL to access a single Object in a bucket. This can be used to share objects, and also to create/delete objects by using the appropriate HTTP method in your request body's `method` parameter.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 
**bucket** | **string**| The bucket name. | 
 **optional** | ***CreateObjectStorageObjectURLOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a CreateObjectStorageObjectURLOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| Information about the request to sign. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## DeleteObjectStorageBucket

> map[string]interface{} DeleteObjectStorageBucket(ctx, clusterId, bucket)

Remove Object Storage Bucket

Removes a single bucket. While buckets containing objects _may_ be deleted by including the `force` option in the request, such operations will fail if the bucket contains too many objects. The recommended way to empty large buckets is to use the [S3 API to configure lifecycle policies](https://docs.ceph.com/docs/master/radosgw/bucketpolicy/#) that remove all objects, then delete the bucket.  This endpoint is available for convenience. It is recommended that instead you use the more [fully- featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/bucketops/#delete-bucket) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 
**bucket** | **string**| The bucket name. | 

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


## DeleteObjectStorageKey

> map[string]interface{} DeleteObjectStorageKey(ctx, keyId)

Revoke Object Storage Key

Revokes an Object Storage Key.  This keypair will no longer be usable by third-party clients. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**keyId** | **int32**| The key to look up. | 

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


## GetObjectStorageBucket

> ObjectStorageBucket GetObjectStorageBucket(ctx, clusterId, bucket)

View Object Storage Bucket

Returns a single Object Storage Bucket.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/bucketops/#get-bucket) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 
**bucket** | **string**| The bucket name. | 

### Return type

[**ObjectStorageBucket**](ObjectStorageBucket.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageBucketContent

> map[string]interface{} GetObjectStorageBucketContent(ctx, clusterId, bucket, optional)

List Object Storage Bucket Contents

Returns the contents of a bucket. The contents are paginated using a `marker`, which is the name of the last object on the previous page.  Objects may be filtered by `prefix` and `delimiter` as well; see Query Parameters for more information.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/luminous/radosgw/s3/bucketops/#get-bucket) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 
**bucket** | **string**| The bucket name. | 
 **optional** | ***GetObjectStorageBucketContentOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a GetObjectStorageBucketContentOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **marker** | **optional.String**| The \&quot;marker\&quot; for this request, which can be used to paginate through large buckets. Its value should be the value of the &#x60;next_marker&#x60; property returned with the last page. Listing bucket contents *does not* support arbitrary page access. See the &#x60;next_marker&#x60; property in the responses section for more details.  | 
 **delimiter** | **optional.String**| The delimiter for object names; if given, object names will be returned up to the first occurrence of this character. This is most commonly used with the &#x60;/&#x60; character to allow bucket transversal in a manner similar to a filesystem, however any delimiter may be used. Use in conjunction with &#x60;prefix&#x60; to see object names past the first occurrence of the delimiter.  | 
 **prefix** | **optional.String**| Filters objects returned to only those whose name start with the given prefix. Commonly used in conjunction with &#x60;delimiter&#x60; to allow transversal of bucket contents in a manner similar to a filesystem.  | 
 **pageSize** | **optional.Int32**| The number of items to return per page. | [default to 100]

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


## GetObjectStorageBucketinCluster

> InlineResponse20040 GetObjectStorageBucketinCluster(ctx, clusterId)

List Object Storage Buckets in Cluster

Returns a list of Buckets in this cluster belonging to this Account.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/bucketops/#get-bucket) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 

### Return type

[**InlineResponse20040**](inline_response_200_40.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageBuckets

> InlineResponse20040 GetObjectStorageBuckets(ctx, )

List Object Storage Buckets

Returns a paginated list of all Object Storage Buckets that you own.   This endpoint is available for convenience. It is recommended that instead you use the more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/serviceops/) directly. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20040**](inline_response_200_40.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageCluster

> ObjectStorageCluster GetObjectStorageCluster(ctx, clusterId)

View Cluster

Returns a single Object Storage Cluster. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the Cluster. | 

### Return type

[**ObjectStorageCluster**](ObjectStorageCluster.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageClusters

> InlineResponse20041 GetObjectStorageClusters(ctx, )

List Clusters

Returns a paginated list of Object Storage Clusters that are available for use.  Users can connect to the clusters with third party clients to create buckets and upload objects. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20041**](inline_response_200_41.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageKey

> ObjectStorageKey GetObjectStorageKey(ctx, keyId)

View Object Storage Key

Returns a single Object Storage Key provisioned for your account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**keyId** | **int32**| The key to look up. | 

### Return type

[**ObjectStorageKey**](ObjectStorageKey.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## GetObjectStorageKeys

> InlineResponse20042 GetObjectStorageKeys(ctx, )

List Object Storage Keys

Returns a paginated list of Object Storage Keys for authenticating to the Object Storage S3 API. 

### Required Parameters

This endpoint does not need any parameter.

### Return type

[**InlineResponse20042**](inline_response_200_42.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## ModifyObjectStorageBucketAccess

> map[string]interface{} ModifyObjectStorageBucketAccess(ctx, clusterId, bucket, optional)

Modify Object Storage Bucket Access

Allows changing basic Cross-origin Resource Sharing (CORS) and Access Control Level (ACL) settings. Only allows enabling/disabling CORS for all origins, and/or setting canned ACLs. For more fine-grained control of both systems, please use the S3 API directly.   This endpoint is available for convenience. It is recommended that instead you use the more more [fully-featured S3 API](https://docs.ceph.com/docs/mimic/radosgw/s3/bucketops/#put-bucket-acl) directly. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**clusterId** | **string**| The ID of the cluster this bucket exists in. | 
**bucket** | **string**| The bucket name. | 
 **optional** | ***ModifyObjectStorageBucketAccessOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a ModifyObjectStorageBucketAccessOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------


 **uNKNOWNBASETYPE** | [**optional.Interface of UNKNOWN_BASE_TYPE**](UNKNOWN_BASE_TYPE.md)| The changes to make to the bucket&#39;s access controls. | 

### Return type

[**map[string]interface{}**](map[string]interface{}.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)


## UpdateObjectStorageKey

> ObjectStorageKey UpdateObjectStorageKey(ctx, keyId, optional)

Update an Object Storage Key

Updates an Object Storage Key on your account. 

### Required Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
**ctx** | **context.Context** | context for authentication, logging, cancellation, deadlines, tracing, etc.
**keyId** | **int32**| The key to look up. | 
 **optional** | ***UpdateObjectStorageKeyOpts** | optional parameters | nil if no parameters

### Optional Parameters

Optional parameters are passed through a pointer to a UpdateObjectStorageKeyOpts struct


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------

 **objectStorageKey** | [**optional.Interface of ObjectStorageKey**](ObjectStorageKey.md)| The fields to update. | 

### Return type

[**ObjectStorageKey**](ObjectStorageKey.md)

### Authorization

[oauth](../README.md#oauth), [personalAccessToken](../README.md#personalAccessToken)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints)
[[Back to Model list]](../README.md#documentation-for-models)
[[Back to README]](../README.md)

