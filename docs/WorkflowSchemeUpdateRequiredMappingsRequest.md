# WorkflowSchemeUpdateRequiredMappingsRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**default_workflow_id** | **str** | The ID of the new default workflow for this workflow scheme. Only used in global-scoped workflow schemes. If it isn&#x27;t specified, is set to *Jira Workflow (jira)*. | [optional] 
**id** | **str** | The ID of the workflow scheme. | 
**workflows_for_issue_types** | [**list[WorkflowSchemeAssociation]**](WorkflowSchemeAssociation.md) | The new workflow to issue type mappings for this workflow scheme. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

