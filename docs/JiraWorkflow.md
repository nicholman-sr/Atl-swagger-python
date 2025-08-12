# JiraWorkflow

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**created** | **str** | The creation date of the workflow. | [optional] 
**description** | **str** | The description of the workflow. | [optional] 
**id** | **str** | The ID of the workflow. | [optional] 
**is_editable** | **bool** | Indicates if the workflow can be edited. | [optional] 
**looped_transition_container_layout** | [**WorkflowLayout**](WorkflowLayout.md) |  | [optional] 
**name** | **str** | The name of the workflow. | [optional] 
**scope** | [**WorkflowScope**](WorkflowScope.md) |  | [optional] 
**start_point_layout** | [**WorkflowLayout**](WorkflowLayout.md) |  | [optional] 
**statuses** | [**list[WorkflowReferenceStatus]**](WorkflowReferenceStatus.md) | The statuses referenced in this workflow. | [optional] 
**task_id** | **str** | If there is a current [asynchronous task](#async-operations) operation for this workflow. | [optional] 
**transitions** | [**list[WorkflowTransitions]**](WorkflowTransitions.md) | The transitions of the workflow. Note that a transition can have either the deprecated &#x60;to&#x60;/&#x60;from&#x60; fields or the &#x60;toStatusReference&#x60;/&#x60;links&#x60; fields, but never both nor a combination. | [optional] 
**updated** | **str** | The last edited date of the workflow. | [optional] 
**version** | [**DocumentVersion**](DocumentVersion.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

