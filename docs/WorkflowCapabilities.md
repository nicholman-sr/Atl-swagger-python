# WorkflowCapabilities

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**connect_rules** | [**list[AvailableWorkflowConnectRule]**](AvailableWorkflowConnectRule.md) | The Connect provided ecosystem rules available. | [optional] 
**editor_scope** | **str** | The scope of the workflow capabilities. &#x60;GLOBAL&#x60; for company-managed projects and &#x60;PROJECT&#x60; for team-managed projects. | [optional] 
**forge_rules** | [**list[AvailableWorkflowForgeRule]**](AvailableWorkflowForgeRule.md) | The Forge provided ecosystem rules available. | [optional] 
**project_types** | **list[str]** | The types of projects that this capability set is available for. | [optional] 
**system_rules** | [**list[AvailableWorkflowSystemRule]**](AvailableWorkflowSystemRule.md) | The Atlassian provided system rules available. | [optional] 
**trigger_rules** | [**list[AvailableWorkflowTriggers]**](AvailableWorkflowTriggers.md) | The trigger rules available. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

