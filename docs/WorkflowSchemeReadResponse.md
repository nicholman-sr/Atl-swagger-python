# WorkflowSchemeReadResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**default_workflow** | [**WorkflowMetadataRestModel**](WorkflowMetadataRestModel.md) |  | [optional] 
**description** | **str** | The description of the workflow scheme. | [optional] 
**id** | **str** | The ID of the workflow scheme. | 
**name** | **str** | The name of the workflow scheme. | 
**scope** | [**WorkflowScope**](WorkflowScope.md) |  | 
**task_id** | **str** | Indicates if there&#x27;s an [asynchronous task](#async-operations) for this workflow scheme. | [optional] 
**version** | [**DocumentVersion**](DocumentVersion.md) |  | 
**workflows_for_issue_types** | [**list[WorkflowMetadataAndIssueTypeRestModel]**](WorkflowMetadataAndIssueTypeRestModel.md) | Mappings from workflows to issue types. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

