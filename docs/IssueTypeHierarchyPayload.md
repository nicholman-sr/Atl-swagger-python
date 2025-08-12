# IssueTypeHierarchyPayload

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hierarchy_level** | **int** | The hierarchy level of the issue type. 0, 1, 2, 3 .. n; Negative values for subtasks | [optional] 
**name** | **str** | The name of the issue type | [optional] 
**on_conflict** | **str** | The conflict strategy to use when the issue type already exists. FAIL - Fail execution, this always needs to be unique; USE - Use the existing entity and ignore new entity parameters | [optional] 
**pcri** | [**ProjectCreateResourceIdentifier**](ProjectCreateResourceIdentifier.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

