# UserDetails

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **str** | The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. | [optional] 
**account_type** | **str** | The type of account represented by this user. This will be one of &#x27;atlassian&#x27; (normal users), &#x27;app&#x27; (application user) or &#x27;customer&#x27; (Jira Service Desk customer user) | [optional] 
**active** | **bool** | Whether the user is active. | [optional] 
**avatar_urls** | **AllOfUserDetailsAvatarUrls** | The avatars of the user. | [optional] 
**display_name** | **str** | The display name of the user. Depending on the user’s privacy settings, this may return an alternative value. | [optional] 
**email_address** | **str** | The email address of the user. Depending on the user’s privacy settings, this may be returned as null. | [optional] 
**key** | **str** | This property is no longer available and will be removed from the documentation soon. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 
**name** | **str** | This property is no longer available and will be removed from the documentation soon. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 
**_self** | **str** | The URL of the user. | [optional] 
**time_zone** | **str** | The time zone specified in the user&#x27;s profile. Depending on the user’s privacy settings, this may be returned as null. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

