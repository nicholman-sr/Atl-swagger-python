# GetPlanResponse

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**cross_project_releases** | [**list[GetCrossProjectReleaseResponse]**](GetCrossProjectReleaseResponse.md) | The cross-project releases included in the plan. | [optional] 
**custom_fields** | [**list[GetCustomFieldResponse]**](GetCustomFieldResponse.md) | The custom fields for the plan. | [optional] 
**exclusion_rules** | **AllOfGetPlanResponseExclusionRules** | The exclusion rules for the plan. | [optional] 
**id** | **int** | The plan ID. | 
**issue_sources** | [**list[GetIssueSourceResponse]**](GetIssueSourceResponse.md) | The issue sources included in the plan. | [optional] 
**last_saved** | **str** | The date when the plan was last saved in UTC. | [optional] 
**lead_account_id** | **str** | The account ID of the plan lead. | [optional] 
**name** | **str** | The plan name. | [optional] 
**permissions** | [**list[GetPermissionResponse]**](GetPermissionResponse.md) | The permissions for the plan. | [optional] 
**scheduling** | **AllOfGetPlanResponseScheduling** | The scheduling settings for the plan. | 
**status** | **str** | The plan status. This is \&quot;Active\&quot;, \&quot;Trashed\&quot; or \&quot;Archived\&quot;. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

