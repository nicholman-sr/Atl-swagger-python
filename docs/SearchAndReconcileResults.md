# SearchAndReconcileResults

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**is_last** | **bool** | Indicates whether this is the last page of the paginated response. | [optional] 
**issues** | [**list[IssueBean]**](IssueBean.md) | The list of issues found by the search or reconsiliation. | [optional] 
**names** | **dict(str, str)** | The ID and name of each field in the search results. | [optional] 
**next_page_token** | **str** | Continuation token to fetch the next page. If this result represents the last or the only page this token will be null. This token will expire in 7 days. | [optional] 
**schema** | [**dict(str, JsonTypeBean)**](JsonTypeBean.md) | The schema describing the field types in the search results. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

