# CreateWorkflowTransitionDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**description** | **str** | The description of the transition. The maximum length is 1000 characters. | [optional] 
**_from** | **list[str]** | The statuses the transition can start from. | [optional] 
**name** | **str** | The name of the transition. The maximum length is 60 characters. | 
**properties** | **dict(str, str)** | The properties of the transition. | [optional] 
**rules** | **AllOfCreateWorkflowTransitionDetailsRules** | The rules of the transition. | [optional] 
**screen** | **AllOfCreateWorkflowTransitionDetailsScreen** | The screen of the transition. | [optional] 
**to** | **str** | The status the transition goes to. | 
**type** | **str** | The type of the transition. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

