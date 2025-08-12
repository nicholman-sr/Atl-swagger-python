# WorkflowTransitions

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actions** | [**list[WorkflowRuleConfiguration]**](WorkflowRuleConfiguration.md) | The post-functions of the transition. | [optional] 
**conditions** | [**ConditionGroupConfiguration**](ConditionGroupConfiguration.md) |  | [optional] 
**custom_issue_event_id** | **str** | The custom event ID of the transition. | [optional] 
**description** | **str** | The description of the transition. | [optional] 
**id** | **str** | The ID of the transition. | [optional] 
**links** | [**list[WorkflowTransitionLinks]**](WorkflowTransitionLinks.md) | The statuses the transition can start from, and the mapping of ports between the statuses. | [optional] 
**name** | **str** | The name of the transition. | [optional] 
**properties** | **dict(str, str)** | The properties of the transition. | [optional] 
**to_status_reference** | **str** | The status the transition goes to. | [optional] 
**transition_screen** | [**WorkflowRuleConfiguration**](WorkflowRuleConfiguration.md) |  | [optional] 
**triggers** | [**list[WorkflowTrigger]**](WorkflowTrigger.md) | The triggers of the transition. | [optional] 
**type** | **str** | The transition type. | [optional] 
**validators** | [**list[WorkflowRuleConfiguration]**](WorkflowRuleConfiguration.md) | The validators of the transition. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

