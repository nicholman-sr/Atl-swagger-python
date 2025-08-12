# TransitionPayload

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actions** | [**list[RulePayload]**](RulePayload.md) | The actions that are performed when the transition is made | [optional] 
**conditions** | [**ConditionGroupPayload**](ConditionGroupPayload.md) |  | [optional] 
**custom_issue_event_id** | **str** | Mechanism in Jira for triggering certain actions, like notifications, automations, etc. Unless a custom notification scheme is configure, it&#x27;s better not to provide any value here | [optional] 
**description** | **str** | The description of the transition | [optional] 
**_from** | [**list[FromLayoutPayload]**](FromLayoutPayload.md) | The statuses that the transition can be made from | [optional] 
**id** | **int** | The id of the transition | [optional] 
**name** | **str** | The name of the transition | [optional] 
**properties** | **dict(str, str)** | The properties of the transition | [optional] 
**to** | [**ToLayoutPayload**](ToLayoutPayload.md) |  | [optional] 
**transition_screen** | [**RulePayload**](RulePayload.md) |  | [optional] 
**triggers** | [**list[RulePayload]**](RulePayload.md) | The triggers that are performed when the transition is made | [optional] 
**type** | **str** | The type of the transition | [optional] 
**validators** | [**list[RulePayload]**](RulePayload.md) | The validators that are performed when the transition is made | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

