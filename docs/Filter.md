# Filter

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**approximate_last_used** | **datetime** | \\[Experimental\\] Approximate last used time. Returns the date and time when the filter was last used. Returns &#x60;null&#x60; if the filter hasn&#x27;t been used after tracking was enabled. For performance reasons, timestamps aren&#x27;t updated in real time and therefore may not be exactly accurate. | [optional] 
**description** | **str** | A description of the filter. | [optional] 
**edit_permissions** | [**list[SharePermission]**](SharePermission.md) | The groups and projects that can edit the filter. | [optional] 
**favourite** | **bool** | Whether the filter is selected as a favorite. | [optional] 
**favourited_count** | **int** | The count of how many users have selected this filter as a favorite, including the filter owner. | [optional] 
**id** | **str** | The unique identifier for the filter. | [optional] 
**jql** | **str** | The JQL query for the filter. For example, *project &#x3D; SSP AND issuetype &#x3D; Bug*. | [optional] 
**name** | **str** | The name of the filter. Must be unique. | 
**owner** | **AllOfFilterOwner** | The user who owns the filter. This is defaulted to the creator of the filter, however Jira administrators can change the owner of a shared filter in the admin settings. | [optional] 
**search_url** | **str** | A URL to view the filter results in Jira, using the [Search for issues using JQL](#api-rest-api-3-filter-search-get) operation with the filter&#x27;s JQL string to return the filter results. For example, *https://your-domain.atlassian.net/rest/api/3/search?jql&#x3D;project+%3D+SSP+AND+issuetype+%3D+Bug*. | [optional] 
**_self** | **str** | The URL of the filter. | [optional] 
**share_permissions** | [**list[SharePermission]**](SharePermission.md) | The groups and projects that the filter is shared with. | [optional] 
**shared_users** | **AllOfFilterSharedUsers** | A paginated list of the users that the filter is shared with. This includes users that are members of the groups or can browse the projects that the filter is shared with. | [optional] 
**subscriptions** | **AllOfFilterSubscriptions** | A paginated list of the users that are subscribed to the filter. | [optional] 
**view_url** | **str** | A URL to view the filter results in Jira, using the ID of the filter. For example, *https://your-domain.atlassian.net/issues/?filter&#x3D;10100*. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

