# IssueBean

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**changelog** | **AllOfIssueBeanChangelog** | Details of changelogs associated with the issue. | [optional] 
**editmeta** | **AllOfIssueBeanEditmeta** | The metadata for the fields on the issue that can be amended. | [optional] 
**expand** | **str** | Expand options that include additional issue details in the response. | [optional] 
**fields** | **dict(str, object)** |  | [optional] 
**fields_to_include** | [**IncludedFields**](IncludedFields.md) |  | [optional] 
**id** | **str** | The ID of the issue. | [optional] 
**key** | **str** | The key of the issue. | [optional] 
**names** | **dict(str, str)** | The ID and name of each field present on the issue. | [optional] 
**operations** | **AllOfIssueBeanOperations** | The operations that can be performed on the issue. | [optional] 
**properties** | **dict(str, object)** | Details of the issue properties identified in the request. | [optional] 
**rendered_fields** | **dict(str, object)** | The rendered value of each field present on the issue. | [optional] 
**schema** | [**dict(str, JsonTypeBean)**](JsonTypeBean.md) | The schema describing each field present on the issue. | [optional] 
**_self** | **str** | The URL of the issue details. | [optional] 
**transitions** | [**list[IssueTransition]**](IssueTransition.md) | The transitions that can be performed on the issue. | [optional] 
**versioned_representations** | **dict(str, dict(str, object))** | The versions of each field on the issue. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

