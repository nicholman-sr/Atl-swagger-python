# BulkEditShareableEntityRequest

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**action** | **str** | Allowed action for bulk edit shareable entity | 
**change_owner_details** | **AllOfBulkEditShareableEntityRequestChangeOwnerDetails** | The details of change owner action. | [optional] 
**entity_ids** | **list[int]** | The id list of shareable entities to be changed. | 
**extend_admin_permissions** | **bool** | Whether the actions are executed by users with Administer Jira global permission. | [optional] 
**permission_details** | **AllOfBulkEditShareableEntityRequestPermissionDetails** | The permission details to be changed. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

