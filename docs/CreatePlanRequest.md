# CreatePlanRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cross_project_releases** | [**list[CreateCrossProjectReleaseRequest]**](CreateCrossProjectReleaseRequest.md) | The cross-project releases to include in the plan. | [optional] 
**custom_fields** | [**list[CreateCustomFieldRequest]**](CreateCustomFieldRequest.md) | The custom fields for the plan. | [optional] 
**exclusion_rules** | **AllOfCreatePlanRequestExclusionRules** | The exclusion rules for the plan. | [optional] 
**issue_sources** | [**list[CreateIssueSourceRequest]**](CreateIssueSourceRequest.md) | The issue sources to include in the plan. | 
**lead_account_id** | **str** | The account ID of the plan lead. | [optional] 
**name** | **str** | The plan name. | 
**permissions** | [**list[CreatePermissionRequest]**](CreatePermissionRequest.md) | The permissions for the plan. | [optional] 
**scheduling** | **AllOfCreatePlanRequestScheduling** | The scheduling settings for the plan. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

