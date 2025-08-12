# WorkflowTransitionRulesUpdateErrorDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rule_update_errors** | **dict(str, list[str])** | A list of transition rule update errors, indexed by the transition rule ID. Any transition rule that appears here wasn&#x27;t updated. | 
**update_errors** | **list[str]** | The list of errors that specify why the workflow update failed. The workflow was not updated if the list contains any entries. | 
**workflow_id** | [**WorkflowId**](WorkflowId.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

