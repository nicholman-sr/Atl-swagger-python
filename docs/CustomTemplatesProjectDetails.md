# CustomTemplatesProjectDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**access_level** | **str** | The access level of the project. Only used by team-managed project | [optional] 
**additional_properties** | **dict(str, str)** | Additional properties of the project | [optional] 
**assignee_type** | **str** | The default assignee when creating issues in the project | [optional] 
**avatar_id** | **int** | The ID of the project&#x27;s avatar. Use the \\[Get project avatars\\](\\#api-rest-api-3-project-projectIdOrKey-avatar-get) operation to list the available avatars in a project. | [optional] 
**category_id** | **int** | The ID of the project&#x27;s category. A complete list of category IDs is found using the [Get all project categories](#api-rest-api-3-projectCategory-get) operation. | [optional] 
**description** | **str** | Brief description of the project | [optional] 
**enable_components** | **bool** | Whether components are enabled for the project. Only used by company-managed project | [optional] [default to False]
**key** | **str** | Project keys must be unique and start with an uppercase letter followed by one or more uppercase alphanumeric characters. The maximum length is 10 characters. | [optional] 
**language** | **str** | The default language for the project | [optional] 
**lead_account_id** | **str** | The account ID of the project lead. Either &#x60;lead&#x60; or &#x60;leadAccountId&#x60; must be set when creating a project. Cannot be provided with &#x60;lead&#x60;. | [optional] 
**name** | **str** | Name of the project | [optional] 
**url** | **str** | A link to information about this project, such as project documentation | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

