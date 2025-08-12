# AuditRecordBean

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**associated_items** | [**list[AssociatedItemBean]**](AssociatedItemBean.md) | The list of items associated with the changed record. | [optional] 
**author_key** | **str** | Deprecated, use &#x60;authorAccountId&#x60; instead. The key of the user who created the audit record. | [optional] 
**category** | **str** | The category of the audit record. For a list of these categories, see the help article [Auditing in Jira applications](https://confluence.atlassian.com/x/noXKM). | [optional] 
**changed_values** | [**list[ChangedValueBean]**](ChangedValueBean.md) | The list of values changed in the record event. | [optional] 
**created** | **datetime** | The date and time on which the audit record was created. | [optional] 
**description** | **str** | The description of the audit record. | [optional] 
**event_source** | **str** | The event the audit record originated from. | [optional] 
**id** | **int** | The ID of the audit record. | [optional] 
**object_item** | [**AssociatedItemBean**](AssociatedItemBean.md) |  | [optional] 
**remote_address** | **str** | The URL of the computer where the creation of the audit record was initiated. | [optional] 
**summary** | **str** | The summary of the audit record. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

