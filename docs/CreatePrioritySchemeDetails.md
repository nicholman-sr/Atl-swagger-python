# CreatePrioritySchemeDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**default_priority_id** | **int** | The ID of the default priority for the priority scheme. | 
**description** | **str** | The description of the priority scheme. | [optional] 
**mappings** | **AllOfCreatePrioritySchemeDetailsMappings** | Instructions to migrate the priorities of issues.  &#x60;in&#x60; mappings are used to migrate the priorities of issues to priorities used within the priority scheme.  &#x60;out&#x60; mappings are used to migrate the priorities of issues to priorities not used within the priority scheme.   *  When **priorities** are **added** to the new priority scheme, no mapping needs to be provided as the new priorities are not used by any issues.  *  When **priorities** are **removed** from the new priority scheme, no mapping needs to be provided as the removed priorities are not used by any issues.  *  When **projects** are **added** to the priority scheme, the priorities of issues in those projects might need to be migrated to new priorities used by the priority scheme. This can occur when the current scheme does not use all the priorities in the project(s)&#x27; priority scheme(s).           *  An &#x60;in&#x60; mapping must be provided for each of these priorities.  *  When **projects** are **removed** from the priority scheme, no mapping needs to be provided as the removed projects are not using the priorities of the new priority scheme.  For more information on &#x60;in&#x60; and &#x60;out&#x60; mappings, see the child properties documentation for the &#x60;PriorityMapping&#x60; object below. | [optional] 
**name** | **str** | The name of the priority scheme. Must be unique. | 
**priority_ids** | **list[int]** | The IDs of priorities in the scheme. | 
**project_ids** | **list[int]** | The IDs of projects that will use the priority scheme. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

