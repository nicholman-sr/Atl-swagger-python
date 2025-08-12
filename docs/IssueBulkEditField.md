# IssueBulkEditField

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**description** | **str** | Description of the field. | [optional] 
**field_options** | [**list[IssueBulkOperationsFieldOption]**](IssueBulkOperationsFieldOption.md) | A list of options related to the field, applicable in contexts where multiple selections are allowed. | [optional] 
**id** | **str** | The unique ID of the field. | [optional] 
**is_required** | **bool** | Indicates whether the field is mandatory for the operation. | [optional] 
**multi_select_field_options** | **list[str]** | Specifies supported actions (like add, replace, remove) on multi-select fields via an enum. | [optional] 
**name** | **str** | The display name of the field. | [optional] 
**search_url** | **str** | A URL to fetch additional data for the field | [optional] 
**type** | **str** | The type of the field. | [optional] 
**unavailable_message** | **str** | A message indicating why the field is unavailable for editing. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

