# NodeBalancerNode

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This node&#39;s unique ID. | [optional] [readonly] 
**Address** | **string** | The private IP Address where this backend can be reached. This _must_ be a private IP address.  | [optional] 
**Label** | **string** | The label for this node.  This is for display purposes only.  | [optional] 
**Status** | **string** | The current status of this node, based on the configured checks of its NodeBalancer Config.  | [optional] [readonly] 
**Weight** | **int32** | Used when picking a backend to serve a request and is not pinned to a single backend yet.  Nodes with a higher weight will receive more traffic.  | [optional] 
**Mode** | **string** | The mode this NodeBalancer should use when sending traffic to this backend. * If set to &#x60;accept&#x60; this backend is accepting traffic. * If set to &#x60;reject&#x60; this backend will not receive traffic. * If set to &#x60;drain&#x60; this backend will not receive _new_ traffic, but connections already   pinned to it will continue to be routed to it.  * If set to &#x60;backup&#x60;, this backend will only receive traffic if all &#x60;accept&#x60; nodes   are down.  | [optional] 
**ConfigId** | **int32** | The NodeBalancer Config ID that this Node belongs to.  | [optional] [readonly] 
**NodebalancerId** | **int32** | The NodeBalancer ID that this Node belongs to.  | [optional] [readonly] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


