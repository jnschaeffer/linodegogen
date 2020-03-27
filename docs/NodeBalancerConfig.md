# NodeBalancerConfig

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int32** | This config&#39;s unique ID | [optional] [readonly] 
**Port** | **int32** | The port this Config is for. These values must be unique across configs on a single NodeBalancer (you can&#39;t have two configs for port 80, for example).  While some ports imply some protocols, no enforcement is done and you may configure your NodeBalancer however is useful to you. For example, while port 443 is generally used for HTTPS, you do not need SSL configured to have a NodeBalancer listening on port 443.  | [optional] 
**Protocol** | **string** | The protocol this port is configured to serve. * If using &#x60;http&#x60; or &#x60;tcp&#x60; protocol, &#x60;ssl_cert&#x60; and &#x60;ssl_key&#x60; are not supported. * If using &#x60;https&#x60; protocol, &#x60;ssl_cert&#x60; and &#x60;ssl_key&#x60; are required.  | [optional] 
**Algorithm** | **string** | What algorithm this NodeBalancer should use for routing traffic to backends.  | [optional] 
**Stickiness** | **string** | Controls how session stickiness is handled on this port. * If set to &#x60;none&#x60; connections will always be assigned a backend based on the algorithm configured. * If set to &#x60;table&#x60; sessions from the same remote address will be routed to the same   backend.  * For HTTP or HTTPS clients, &#x60;http_cookie&#x60; allows sessions to be   routed to the same backend based on a cookie set by the NodeBalancer.  | [optional] 
**Check** | **string** | The type of check to perform against backends to ensure they are serving requests. This is used to determine if backends are up or down. * If &#x60;none&#x60; no check is performed. * &#x60;connection&#x60; requires only a connection to the backend to succeed. * &#x60;http&#x60; and &#x60;http_body&#x60; rely on the backend serving HTTP, and that   the response returned matches what is expected.  | [optional] 
**CheckInterval** | **int32** | How often, in seconds, to check that backends are up and serving requests.  | [optional] 
**CheckTimeout** | **int32** | How long, in seconds, to wait for a check attempt before considering it failed.  | [optional] 
**CheckAttempts** | **int32** | How many times to attempt a check before considering a backend to be down.  | [optional] 
**CheckPath** | **string** | The URL path to check on each backend. If the backend does not respond to this request it is considered to be down.  | [optional] 
**CheckBody** | **string** | This value must be present in the response body of the check in order for it to pass. If this value is not present in the response body of a check request, the backend is considered to be down.  | [optional] 
**CheckPassive** | **bool** | If true, any response from this backend with a &#x60;5xx&#x60; status code will be enough for it to be considered unhealthy and taken out of rotation.  | [optional] 
**CipherSuite** | **string** | What ciphers to use for SSL connections served by this NodeBalancer.  * &#x60;legacy&#x60; is considered insecure and should only be used if necessary.  | [optional] 
**NodebalancerId** | **int32** | The ID for the NodeBalancer this config belongs to.  | [optional] [readonly] 
**SslCommonname** | **string** | The read-only common name automatically derived from the SSL certificate assigned to this NodeBalancerConfig. Please refer to this field to verify that the appropriate certificate is assigned to your NodeBalancerConfig.  | [optional] [readonly] 
**SslFingerprint** | **string** | The read-only fingerprint automatically derived from the SSL certificate assigned to this NodeBalancerConfig. Please refer to this field to verify that the appropriate certificate is assigned to your NodeBalancerConfig.  | [optional] [readonly] 
**SslCert** | Pointer to **string** | The PEM-formatted public SSL certificate (or the combined PEM-formatted SSL certificate and Certificate Authority chain) that should be served on this NodeBalancerConfig&#39;s port.  The contents of this field will not be shown in any responses that display the NodeBalancerConfig. Instead, &#x60;&lt;REDACTED&gt;&#x60; will be printed where the field appears.  The read-only &#x60;ssl_commonname&#x60; and &#x60;ssl_fingerprint&#x60; fields in a NodeBalancerConfig response are automatically derived from your certificate. Please refer to these fields to verify that the appropriate certificate was assigned to your NodeBalancerConfig.  | [optional] 
**SslKey** | Pointer to **string** | The PEM-formatted private key for the SSL certificate set in the &#x60;ssl_cert&#x60; field.  The contents of this field will not be shown in any responses that display the NodeBalancerConfig. Instead, &#x60;&lt;REDACTED&gt;&#x60; will be printed where the field appears.  The read-only &#x60;ssl_commonname&#x60; and &#x60;ssl_fingerprint&#x60; fields in a NodeBalancerConfig response are automatically derived from your certificate. Please refer to these fields to verify that the appropriate certificate was assigned to your NodeBalancerConfig.  | [optional] 
**NodesStatus** | [**NodeBalancerConfigNodesStatus**](NodeBalancerConfig_nodes_status.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


