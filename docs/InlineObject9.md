# InlineObject9

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Label** | **string** | The name for this bucket. Must be unique in the cluster you are creating the bucket in, or an error will be returned. Labels will be reserved only for the cluster that active buckets are created and stored in. If you want to reserve this bucket&#39;s label in another cluster, you must create a new bucket with the same label in the new cluster.  | 
**Cluster** | **string** | The ID of the Object Storage Cluster where this bucket should be created.  | 
**CorsEnabled** | **bool** | If true, the bucket will be created with CORS enabled for all origins. For more fine-grained controls of CORS, use the S3 API directly.  | [optional] [default to false]
**Acl** | **string** | The Access Control Level of the bucket using a canned ACL string. For more fine-grained control of ACLs, use the S3 API directly.  | [optional] [default to ACL_PRIVATE]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


