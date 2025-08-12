# UiModificationContextDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | The ID of the UI modification context. | [optional] 
**is_available** | **bool** | Whether a context is available. For example, when a project is deleted the context becomes unavailable. | [optional] 
**issue_type_id** | **str** | The issue type ID of the context. Null is treated as a wildcard, meaning the UI modification will be applied to all issue types. Each UI modification context can have a maximum of one wildcard. | [optional] 
**project_id** | **str** | The project ID of the context. Null is treated as a wildcard, meaning the UI modification will be applied to all projects. Each UI modification context can have a maximum of one wildcard. | [optional] 
**view_type** | **str** | The view type of the context. Only &#x60;GIC&#x60;(Global Issue Create), &#x60;IssueView&#x60; and &#x60;IssueTransition&#x60; are supported. Null is treated as a wildcard, meaning the UI modification will be applied to all view types. Each UI modification context can have a maximum of one wildcard. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

