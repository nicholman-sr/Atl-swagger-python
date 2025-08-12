# User

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **str** | The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. Required in requests. | [optional] 
**account_type** | **str** | The user account type. Can take the following values:   *  &#x60;atlassian&#x60; regular Atlassian user account  *  &#x60;app&#x60; system account used for Connect applications and OAuth to represent external systems  *  &#x60;customer&#x60; Jira Service Desk account representing an external service desk | [optional] 
**active** | **bool** | Whether the user is active. | [optional] 
**application_roles** | **AllOfUserApplicationRoles** | The application roles the user is assigned to. | [optional] 
**avatar_urls** | **AllOfUserAvatarUrls** | The avatars of the user. | [optional] 
**display_name** | **str** | The display name of the user. Depending on the user’s privacy setting, this may return an alternative value. | [optional] 
**email_address** | **str** | The email address of the user. Depending on the user’s privacy setting, this may be returned as null. | [optional] 
**expand** | **str** | Expand options that include additional user details in the response. | [optional] 
**groups** | **AllOfUserGroups** | The groups that the user belongs to. | [optional] 
**key** | **str** | This property is no longer available and will be removed from the documentation soon. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 
**locale** | **str** | The locale of the user. Depending on the user’s privacy setting, this may be returned as null. | [optional] 
**name** | **str** | This property is no longer available and will be removed from the documentation soon. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 
**_self** | **str** | The URL of the user. | [optional] 
**time_zone** | **str** | The time zone specified in the user&#x27;s profile. If the user&#x27;s time zone is not visible to the current user (due to user&#x27;s profile setting), or if a time zone has not been set, the instance&#x27;s default time zone will be returned. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

