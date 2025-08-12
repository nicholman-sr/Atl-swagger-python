# ProjectRole

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**actors** | [**list[RoleActor]**](RoleActor.md) | The list of users who act in this role. | [optional] 
**admin** | **bool** | Whether this role is the admin role for the project. | [optional] 
**current_user_role** | **bool** | Whether the calling user is part of this role. | [optional] 
**default** | **bool** | Whether this role is the default role for the project | [optional] 
**description** | **str** | The description of the project role. | [optional] 
**id** | **int** | The ID of the project role. | [optional] 
**name** | **str** | The name of the project role. | [optional] 
**role_configurable** | **bool** | Whether the roles are configurable for this project. | [optional] 
**scope** | **AllOfProjectRoleScope** | The scope of the role. Indicated for roles associated with [next-gen projects](https://confluence.atlassian.com/x/loMyO). | [optional] 
**_self** | **str** | The URL the project role details. | [optional] 
**translated_name** | **str** | The translated name of the project role. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

