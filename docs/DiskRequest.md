# DiskRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Size** | **int32** |  | 
**Label** | [**Label**](label.md) |  | 
**Filesystem** | [**Filesystem**](filesystem.md) |  | [optional] 
**ReadOnly** | **bool** | If true, this Disk is read-only.  | [optional] 
**Image** | **string** | An Image ID to deploy the Disk from. Official Linode Images start with &#x60;linode/ &#x60;, while your Images start with &#x60;private/&#x60;. See [/images](/api/v4/images) for more information on the Images available for you to use.  | [optional] 
**AuthorizedKeys** | **[]string** | A list of public SSH keys that will be automatically appended to the root user&#39;s &#x60;~/.ssh/authorized_keys&#x60; file.  | [optional] 
**AuthorizedUsers** | **[]string** | A list of usernames that will have their SSH keys, if any, automatically appended to the root user&#39;s &#x60;~/.ssh/authorized_keys&#x60; file.  | [optional] 
**RootPass** | **string** | This will set the root user&#39;s password on the newly-created Linode. The root password must conform to the following constraints:    * May only use alphanumerics, punctuation, spaces, and tabs.   * Must contain at least two of the following characters classes:     * Upper-case letters     * Lower-case letters     * Digits     * Punctuation   * Must meet a password strength score requirement that is calculated internally by the API.     If the strength requirement is not met, you will receive a &#x60;Password does not meet strength requirement&#x60; error.  | [optional] 
**StackscriptId** | **int32** | A StackScript ID that will cause the referenced StackScript to be run during deployment of this Linode. A compatible &#x60;image&#x60; is required to use a StackScript. To get a list of available StackScript and their permitted Images see [/stackscripts](/api/v4/linode-stackscripts). This field cannot be used when deploying from a Backup or a private Image.  | [optional] 
**StackscriptData** | [**map[string]interface{}**](.md) | This field is required only if the StackScript being deployed requires input data from the User for successful completion. See &lt;a target&#x3D;\&quot;_top\&quot; href&#x3D;\&quot;https://www.linode.com/docs/platform/stackscripts/#variables-and-udfs\&quot;&gt;Variables and UDFs&lt;/a&gt; for more details. This field is required to be valid JSON.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


