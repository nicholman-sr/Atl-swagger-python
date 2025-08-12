# UpdateProjectDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**assignee_type** | **str** | The default assignee when creating issues for this project. | [optional] 
**avatar_id** | **int** | An integer value for the project&#x27;s avatar. | [optional] 
**category_id** | **int** | The ID of the project&#x27;s category. A complete list of category IDs is found using the [Get all project categories](#api-rest-api-3-projectCategory-get) operation. To remove the project category from the project, set the value to &#x60;-1.&#x60; | [optional] 
**description** | **str** | A brief description of the project. | [optional] 
**issue_security_scheme** | **int** | The ID of the issue security scheme for the project, which enables you to control who can and cannot view issues. Use the [Get issue security schemes](#api-rest-api-3-issuesecurityschemes-get) resource to get all issue security scheme IDs. | [optional] 
**key** | **str** | Project keys must be unique and start with an uppercase letter followed by one or more uppercase alphanumeric characters. The maximum length is 10 characters. | [optional] 
**lead** | **str** | This parameter is deprecated because of privacy changes. Use &#x60;leadAccountId&#x60; instead. See the [migration guide](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. The user name of the project lead. Cannot be provided with &#x60;leadAccountId&#x60;. | [optional] 
**lead_account_id** | **str** | The account ID of the project lead. Cannot be provided with &#x60;lead&#x60;. | [optional] 
**name** | **str** | The name of the project. | [optional] 
**notification_scheme** | **int** | The ID of the notification scheme for the project. Use the [Get notification schemes](#api-rest-api-3-notificationscheme-get) resource to get a list of notification scheme IDs. | [optional] 
**permission_scheme** | **int** | The ID of the permission scheme for the project. Use the [Get all permission schemes](#api-rest-api-3-permissionscheme-get) resource to see a list of all permission scheme IDs. | [optional] 
**released_project_keys** | **list[str]** | Previous project keys to be released from the current project. Released keys must belong to the current project and not contain the current project key | [optional] 
**url** | **str** | A link to information about this project, such as project documentation | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

