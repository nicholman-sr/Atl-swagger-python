# Workflow

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**created** | **datetime** | The creation date of the workflow. | [optional] 
**description** | **str** | The description of the workflow. | 
**has_draft_workflow** | **bool** | Whether the workflow has a draft version. | [optional] 
**id** | [**PublishedWorkflowId**](PublishedWorkflowId.md) |  | 
**is_default** | **bool** | Whether this is the default workflow. | [optional] 
**operations** | [**WorkflowOperations**](WorkflowOperations.md) |  | [optional] 
**projects** | [**list[ProjectDetails]**](ProjectDetails.md) | The projects the workflow is assigned to, through workflow schemes. | [optional] 
**schemes** | [**list[WorkflowSchemeIdName]**](WorkflowSchemeIdName.md) | The workflow schemes the workflow is assigned to. | [optional] 
**statuses** | [**list[WorkflowStatus]**](WorkflowStatus.md) | The statuses of the workflow. | [optional] 
**transitions** | [**list[Transition]**](Transition.md) | The transitions of the workflow. | [optional] 
**updated** | **datetime** | The last edited date of the workflow. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

