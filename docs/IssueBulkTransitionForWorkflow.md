# IssueBulkTransitionForWorkflow

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**is_transitions_filtered** | **bool** | Indicates whether all the transitions of this workflow are available in the transitions list or not. | [optional] 
**issues** | **list[str]** | List of issue keys from the request which are associated with this workflow. | [optional] 
**transitions** | [**list[SimplifiedIssueTransition]**](SimplifiedIssueTransition.md) | List of transitions available for issues from the request which are associated with this workflow.   **This list includes only those transitions that are common across the issues in this workflow and do not involve any additional field updates.**  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

