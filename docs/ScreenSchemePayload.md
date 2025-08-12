# ScreenSchemePayload

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**default_screen** | [**ProjectCreateResourceIdentifier**](ProjectCreateResourceIdentifier.md) |  | [optional] 
**description** | **str** | The description of the screen scheme | [optional] 
**name** | **str** | The name of the screen scheme | [optional] 
**pcri** | [**ProjectCreateResourceIdentifier**](ProjectCreateResourceIdentifier.md) |  | [optional] 
**screens** | [**dict(str, ProjectCreateResourceIdentifier)**](ProjectCreateResourceIdentifier.md) | Similar to the field layout scheme those mappings allow users to set different screens for different operations: default - always there, applied to all operations that don&#x27;t have an explicit mapping &#x60;create&#x60;, &#x60;view&#x60;, &#x60;edit&#x60; - specific operations that are available and users can assign a different screen for each one of them https://support.atlassian.com/jira-cloud-administration/docs/manage-screen-schemes/\\#Associating-a-screen-with-an-issue-operation | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

