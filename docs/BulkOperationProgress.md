# BulkOperationProgress

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**created** | **datetime** | A timestamp of when the task was submitted. | [optional] 
**failed_accessible_issues** | **dict(str, list[str])** | Map of issue IDs for which the operation failed and that the user has permission to view, to their one or more reasons for failure. These reasons are open-ended text descriptions of the error and are not selected from a predefined list of standard reasons. | [optional] 
**invalid_or_inaccessible_issue_count** | **int** | The number of issues that are either invalid or issues that the user doesn&#x27;t have permission to view, regardless of the success or failure of the operation. | [optional] 
**processed_accessible_issues** | **list[int]** | List of issue IDs for which the operation was successful and that the user has permission to view. | [optional] 
**progress_percent** | **int** | Progress of the task as a percentage. | [optional] 
**started** | **datetime** | A timestamp of when the task was started. | [optional] 
**status** | **str** | The status of the task. | [optional] 
**submitted_by** | [**User**](User.md) |  | [optional] 
**task_id** | **str** | The ID of the task. | [optional] 
**total_issue_count** | **int** | The number of issues that the bulk operation was attempted on. | [optional] 
**updated** | **datetime** | A timestamp of when the task progress was last updated. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

