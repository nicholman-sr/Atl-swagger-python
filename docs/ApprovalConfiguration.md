# ApprovalConfiguration

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**active** | **str** | Whether the approval configuration is active. | 
**condition_type** | **str** | How the required approval count is calculated. It may be configured to require a specific number of approvals, or approval by a percentage of approvers. If the approvers source field is Approver groups, you can configure how many approvals per group are required for the request to be approved. The number will be the same across all groups. | 
**condition_value** | **str** | The number or percentage of approvals required for a request to be approved. If &#x60;conditionType&#x60; is &#x60;number&#x60;, the value must be 20 or less. If &#x60;conditionType&#x60; is &#x60;percent&#x60;, the value must be 100 or less. | 
**exclude** | **list[str]** | A list of roles that should be excluded as possible approvers. | [optional] 
**field_id** | **str** | The custom field ID of the \&quot;Approvers\&quot; or \&quot;Approver Groups\&quot; field. | 
**pre_populated_field_id** | **str** | The custom field ID of the field used to pre-populate the Approver field. Only supports the \&quot;Affected Services\&quot; field. | [optional] 
**transition_approved** | **str** | The numeric ID of the transition to be executed if the request is approved. | 
**transition_rejected** | **str** | The numeric ID of the transition to be executed if the request is declined. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

