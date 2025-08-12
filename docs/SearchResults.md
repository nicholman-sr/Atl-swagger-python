# SearchResults

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**expand** | **str** | Expand options that include additional search result details in the response. | [optional] 
**issues** | [**list[IssueBean]**](IssueBean.md) | The list of issues found by the search. | [optional] 
**max_results** | **int** | The maximum number of results that could be on the page. | [optional] 
**names** | **dict(str, str)** | The ID and name of each field in the search results. | [optional] 
**schema** | [**dict(str, JsonTypeBean)**](JsonTypeBean.md) | The schema describing the field types in the search results. | [optional] 
**start_at** | **int** | The index of the first item returned on the page. | [optional] 
**total** | **int** | The number of results on the page. | [optional] 
**warning_messages** | **list[str]** | Any warnings related to the JQL query. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

