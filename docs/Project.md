# Project

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**archived** | **bool** | Whether the project is archived. | [optional] 
**archived_by** | **AllOfProjectArchivedBy** | The user who archived the project. | [optional] 
**archived_date** | **datetime** | The date when the project was archived. | [optional] 
**assignee_type** | **str** | The default assignee when creating issues for this project. | [optional] 
**avatar_urls** | **AllOfProjectAvatarUrls** | The URLs of the project&#x27;s avatars. | [optional] 
**components** | [**list[ProjectComponent]**](ProjectComponent.md) | List of the components contained in the project. | [optional] 
**deleted** | **bool** | Whether the project is marked as deleted. | [optional] 
**deleted_by** | **AllOfProjectDeletedBy** | The user who marked the project as deleted. | [optional] 
**deleted_date** | **datetime** | The date when the project was marked as deleted. | [optional] 
**description** | **str** | A brief description of the project. | [optional] 
**email** | **str** | An email address associated with the project. | [optional] 
**expand** | **str** | Expand options that include additional project details in the response. | [optional] 
**favourite** | **bool** | Whether the project is selected as a favorite. | [optional] 
**id** | **str** | The ID of the project. | [optional] 
**insight** | **AllOfProjectInsight** | Insights about the project. | [optional] 
**is_private** | **bool** | Whether the project is private from the user&#x27;s perspective. This means the user can&#x27;t see the project or any associated issues. | [optional] 
**issue_type_hierarchy** | **AllOfProjectIssueTypeHierarchy** | The issue type hierarchy for the project. | [optional] 
**issue_types** | [**list[IssueTypeDetails]**](IssueTypeDetails.md) | List of the issue types available in the project. | [optional] 
**key** | **str** | The key of the project. | [optional] 
**landing_page_info** | **AllOfProjectLandingPageInfo** | The project landing page info. | [optional] 
**lead** | **AllOfProjectLead** | The username of the project lead. | [optional] 
**name** | **str** | The name of the project. | [optional] 
**permissions** | **AllOfProjectPermissions** | User permissions on the project | [optional] 
**project_category** | **AllOfProjectProjectCategory** | The category the project belongs to. | [optional] 
**project_type_key** | **str** | The [project type](https://confluence.atlassian.com/x/GwiiLQ#Jiraapplicationsoverview-Productfeaturesandprojecttypes) of the project. | [optional] 
**properties** | **dict(str, object)** | Map of project properties | [optional] 
**retention_till_date** | **datetime** | The date when the project is deleted permanently. | [optional] 
**roles** | **dict(str, str)** | The name and self URL for each role defined in the project. For more information, see [Create project role](#api-rest-api-3-role-post). | [optional] 
**_self** | **str** | The URL of the project details. | [optional] 
**simplified** | **bool** | Whether the project is simplified. | [optional] 
**style** | **str** | The type of the project. | [optional] 
**url** | **str** | A link to information about this project, such as project documentation. | [optional] 
**uuid** | **str** | Unique ID for next-gen projects. | [optional] 
**versions** | [**list[Version]**](Version.md) | The versions defined in the project. For more information, see [Create version](#api-rest-api-3-version-post). | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

