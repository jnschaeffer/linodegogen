# LinodeType

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **string** | The ID representing the Linode Type. | [optional] [readonly] 
**Label** | **string** | The Linode Type&#39;s label is for display purposes only.  | [optional] [readonly] 
**Disk** | **int32** | The Disk size, in MB, of the Linode Type.  | [optional] [readonly] 
**Class** | **string** | The class of the Linode Type. We currently offer five classes of Linodes:    * nanode - Nanode instances are good for low-duty workloads,     where performance isn&#39;t critical.   * standard - Standard instances are good for medium-duty workloads and     are a good mix of performance, resources, and price.   * dedicated - Dedicated CPU instances are good for full-duty workloads     where consistent performance is important.   * gpu - Linodes with dedicated NVIDIA Quadro &amp;reg; RTX 6000 GPUs accelerate highly     specialized applications such as machine learning, AI, and video transcoding.   * highmem - High Memory instances favor RAM over other resources, and can be     good for memory hungry use cases like caching and in-memory databases.  | [optional] [readonly] 
**Price** | [**LinodeTypePrice**](LinodeType_price.md) |  | [optional] 
**Addons** | [**LinodeTypeAddons**](LinodeType_addons.md) |  | [optional] 
**NetworkOut** | **int32** | The Mbits outbound bandwidth allocation.  | [optional] [readonly] 
**Memory** | **int32** | Amount of RAM included in this Linode Type.  | [optional] [readonly] 
**Successor** | Pointer to **string** | The Linode Type that a [mutate](/api/v4/linode-instances-linode-id-mutate/#post) will upgrade to for a Linode of this type.  If \&quot;null\&quot;, a Linode of this type may not mutate.  | [optional] [readonly] 
**Transfer** | **int32** | The monthly outbound transfer amount, in MB.  | [optional] [readonly] 
**Vcpus** | **int32** | The number of VCPU cores this Linode Type offers.  | [optional] [readonly] 
**Gpus** | **int32** | The number of GPUs this Linode Type offers.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


