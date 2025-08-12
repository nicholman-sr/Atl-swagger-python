# JiraExpressionForAnalysis

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**context_variables** | **dict(str, str)** | Context variables and their types. The type checker assumes that [common context variables](https://developer.atlassian.com/cloud/jira/platform/jira-expressions/#context-variables), such as &#x60;issue&#x60; or &#x60;project&#x60;, are available in context and sets their type. Use this property to override the default types or provide details of new variables. | [optional] 
**expressions** | **list[str]** | The list of Jira expressions to analyse. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

