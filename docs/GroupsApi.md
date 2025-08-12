# jira_client.GroupsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_user_to_group**](GroupsApi.md#add_user_to_group) | **POST** /rest/api/3/group/user | Add user to group
[**bulk_get_groups**](GroupsApi.md#bulk_get_groups) | **GET** /rest/api/3/group/bulk | Bulk get groups
[**create_group**](GroupsApi.md#create_group) | **POST** /rest/api/3/group | Create group
[**find_groups**](GroupsApi.md#find_groups) | **GET** /rest/api/3/groups/picker | Find groups
[**get_group**](GroupsApi.md#get_group) | **GET** /rest/api/3/group | Get group
[**get_users_from_group**](GroupsApi.md#get_users_from_group) | **GET** /rest/api/3/group/member | Get users from group
[**remove_group**](GroupsApi.md#remove_group) | **DELETE** /rest/api/3/group | Remove group
[**remove_user_from_group**](GroupsApi.md#remove_user_from_group) | **DELETE** /rest/api/3/group/user | Remove user from group

# **add_user_to_group**
> Group add_user_to_group(body, groupname=groupname, group_id=group_id)

Add user to group

Adds a user to a group.  **[Permissions](#permissions) required:** Site administration (that is, member of the *site-admin* [group](https://confluence.atlassian.com/x/24xjL)).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
body = {
  "accountId" : "5b10ac8d82e05b22cc7d4ef5"
} # dict(str, object) | The user to add to the group.
groupname = 'groupname_example' # str | As a group's name can change, use of `groupId` is recommended to identify a group.   The name of the group. This parameter cannot be used with the `groupId` parameter. (optional)
group_id = 'group_id_example' # str | The ID of the group. This parameter cannot be used with the `groupName` parameter. (optional)

try:
    # Add user to group
    api_response = api_instance.add_user_to_group(body, groupname=groupname, group_id=group_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->add_user_to_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)| The user to add to the group. | 
 **groupname** | **str**| As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended to identify a group.   The name of the group. This parameter cannot be used with the &#x60;groupId&#x60; parameter. | [optional] 
 **group_id** | **str**| The ID of the group. This parameter cannot be used with the &#x60;groupName&#x60; parameter. | [optional] 

### Return type

[**Group**](Group.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulk_get_groups**
> PageBeanGroupDetails bulk_get_groups(start_at=start_at, max_results=max_results, group_id=group_id, group_name=group_name, access_type=access_type, application_key=application_key)

Bulk get groups

Returns a [paginated](#pagination) list of groups.  **[Permissions](#permissions) required:** *Browse users and groups* [global permission](https://confluence.atlassian.com/x/x4dKLg).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
group_id = ['group_id_example'] # list[str] | The ID of a group. To specify multiple IDs, pass multiple `groupId` parameters. For example, `groupId=5b10a2844c20165700ede21g&groupId=5b10ac8d82e05b22cc7d4ef5`. (optional)
group_name = ['group_name_example'] # list[str] | The name of a group. To specify multiple names, pass multiple `groupName` parameters. For example, `groupName=administrators&groupName=jira-software-users`. (optional)
access_type = 'access_type_example' # str | The access level of a group. Valid values: 'site-admin', 'admin', 'user'. (optional)
application_key = 'application_key_example' # str | The application key of the product user groups to search for. Valid values: 'jira-servicedesk', 'jira-software', 'jira-product-discovery', 'jira-core'. (optional)

try:
    # Bulk get groups
    api_response = api_instance.bulk_get_groups(start_at=start_at, max_results=max_results, group_id=group_id, group_name=group_name, access_type=access_type, application_key=application_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->bulk_get_groups: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **group_id** | [**list[str]**](str.md)| The ID of a group. To specify multiple IDs, pass multiple &#x60;groupId&#x60; parameters. For example, &#x60;groupId&#x3D;5b10a2844c20165700ede21g&amp;groupId&#x3D;5b10ac8d82e05b22cc7d4ef5&#x60;. | [optional] 
 **group_name** | [**list[str]**](str.md)| The name of a group. To specify multiple names, pass multiple &#x60;groupName&#x60; parameters. For example, &#x60;groupName&#x3D;administrators&amp;groupName&#x3D;jira-software-users&#x60;. | [optional] 
 **access_type** | **str**| The access level of a group. Valid values: &#x27;site-admin&#x27;, &#x27;admin&#x27;, &#x27;user&#x27;. | [optional] 
 **application_key** | **str**| The application key of the product user groups to search for. Valid values: &#x27;jira-servicedesk&#x27;, &#x27;jira-software&#x27;, &#x27;jira-product-discovery&#x27;, &#x27;jira-core&#x27;. | [optional] 

### Return type

[**PageBeanGroupDetails**](PageBeanGroupDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_group**
> Group create_group(body)

Create group

Creates a group.  **[Permissions](#permissions) required:** Site administration (that is, member of the *site-admin* [group](https://confluence.atlassian.com/x/24xjL)).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
body = {
  "name" : "power-users"
} # dict(str, object) | The name of the group.

try:
    # Create group
    api_response = api_instance.create_group(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->create_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)| The name of the group. | 

### Return type

[**Group**](Group.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_groups**
> FoundGroups find_groups(account_id=account_id, query=query, exclude=exclude, exclude_id=exclude_id, max_results=max_results, case_insensitive=case_insensitive, user_name=user_name, include_teams=include_teams)

Find groups

Returns a list of groups whose names contain a query string. A list of group names can be provided to exclude groups from the results.  The primary use case for this resource is to populate a group picker suggestions list. To this end, the returned object includes the `html` field where the matched query term is highlighted in the group name with the HTML strong tag. Also, the groups list is wrapped in a response object that contains a header for use in the picker, specifically *Showing X of Y matching groups*.  The list returns with the groups sorted. If no groups match the list criteria, an empty list is returned.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg). Anonymous calls and calls by users without the required permission return an empty list.  *Browse users and groups* [global permission](https://confluence.atlassian.com/x/x4dKLg). Without this permission, calls where query is not an exact match to an existing group will return an empty list.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
account_id = 'account_id_example' # str | This parameter is deprecated, setting it does not affect the results. To find groups containing a particular user, use [Get user groups](#api-rest-api-3-user-groups-get). (optional)
query = 'query_example' # str | The string to find in group names. (optional)
exclude = ['exclude_example'] # list[str] | As a group's name can change, use of `excludeGroupIds` is recommended to identify a group.   A group to exclude from the result. To exclude multiple groups, provide an ampersand-separated list. For example, `exclude=group1&exclude=group2`. This parameter cannot be used with the `excludeGroupIds` parameter. (optional)
exclude_id = ['exclude_id_example'] # list[str] | A group ID to exclude from the result. To exclude multiple groups, provide an ampersand-separated list. For example, `excludeId=group1-id&excludeId=group2-id`. This parameter cannot be used with the `excludeGroups` parameter. (optional)
max_results = 56 # int | The maximum number of groups to return. The maximum number of groups that can be returned is limited by the system property `jira.ajax.autocomplete.limit`. (optional)
case_insensitive = false # bool | Whether the search for groups should be case insensitive. (optional) (default to false)
user_name = 'user_name_example' # str | This parameter is no longer available. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. (optional)
include_teams = true # bool |  (optional)

try:
    # Find groups
    api_response = api_instance.find_groups(account_id=account_id, query=query, exclude=exclude, exclude_id=exclude_id, max_results=max_results, case_insensitive=case_insensitive, user_name=user_name, include_teams=include_teams)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->find_groups: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **account_id** | **str**| This parameter is deprecated, setting it does not affect the results. To find groups containing a particular user, use [Get user groups](#api-rest-api-3-user-groups-get). | [optional] 
 **query** | **str**| The string to find in group names. | [optional] 
 **exclude** | [**list[str]**](str.md)| As a group&#x27;s name can change, use of &#x60;excludeGroupIds&#x60; is recommended to identify a group.   A group to exclude from the result. To exclude multiple groups, provide an ampersand-separated list. For example, &#x60;exclude&#x3D;group1&amp;exclude&#x3D;group2&#x60;. This parameter cannot be used with the &#x60;excludeGroupIds&#x60; parameter. | [optional] 
 **exclude_id** | [**list[str]**](str.md)| A group ID to exclude from the result. To exclude multiple groups, provide an ampersand-separated list. For example, &#x60;excludeId&#x3D;group1-id&amp;excludeId&#x3D;group2-id&#x60;. This parameter cannot be used with the &#x60;excludeGroups&#x60; parameter. | [optional] 
 **max_results** | **int**| The maximum number of groups to return. The maximum number of groups that can be returned is limited by the system property &#x60;jira.ajax.autocomplete.limit&#x60;. | [optional] 
 **case_insensitive** | **bool**| Whether the search for groups should be case insensitive. | [optional] [default to false]
 **user_name** | **str**| This parameter is no longer available. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 
 **include_teams** | **bool**|  | [optional] 

### Return type

[**FoundGroups**](FoundGroups.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_group**
> Group get_group(groupname=groupname, group_id=group_id, expand=expand)

Get group

This operation is deprecated, use [`group/member`](#api-rest-api-3-group-member-get).  Returns all users in a group.  **[Permissions](#permissions) required:** either of:   *  *Browse users and groups* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
groupname = 'groupname_example' # str | As a group's name can change, use of `groupId` is recommended to identify a group.   The name of the group. This parameter cannot be used with the `groupId` parameter. (optional)
group_id = 'group_id_example' # str | The ID of the group. This parameter cannot be used with the `groupName` parameter. (optional)
expand = 'expand_example' # str | List of fields to expand. (optional)

try:
    # Get group
    api_response = api_instance.get_group(groupname=groupname, group_id=group_id, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->get_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupname** | **str**| As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended to identify a group.   The name of the group. This parameter cannot be used with the &#x60;groupId&#x60; parameter. | [optional] 
 **group_id** | **str**| The ID of the group. This parameter cannot be used with the &#x60;groupName&#x60; parameter. | [optional] 
 **expand** | **str**| List of fields to expand. | [optional] 

### Return type

[**Group**](Group.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_users_from_group**
> PageBeanUserDetails get_users_from_group(groupname=groupname, group_id=group_id, include_inactive_users=include_inactive_users, start_at=start_at, max_results=max_results)

Get users from group

Returns a [paginated](#pagination) list of all users in a group.  Note that users are ordered by username, however the username is not returned in the results due to privacy reasons.  **[Permissions](#permissions) required:** either of:   *  *Browse users and groups* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
groupname = 'groupname_example' # str | As a group's name can change, use of `groupId` is recommended to identify a group.   The name of the group. This parameter cannot be used with the `groupId` parameter. (optional)
group_id = 'group_id_example' # str | The ID of the group. This parameter cannot be used with the `groupName` parameter. (optional)
include_inactive_users = false # bool | Include inactive users. (optional) (default to false)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page (number should be between 1 and 50). (optional) (default to 50)

try:
    # Get users from group
    api_response = api_instance.get_users_from_group(groupname=groupname, group_id=group_id, include_inactive_users=include_inactive_users, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling GroupsApi->get_users_from_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupname** | **str**| As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended to identify a group.   The name of the group. This parameter cannot be used with the &#x60;groupId&#x60; parameter. | [optional] 
 **group_id** | **str**| The ID of the group. This parameter cannot be used with the &#x60;groupName&#x60; parameter. | [optional] 
 **include_inactive_users** | **bool**| Include inactive users. | [optional] [default to false]
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page (number should be between 1 and 50). | [optional] [default to 50]

### Return type

[**PageBeanUserDetails**](PageBeanUserDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_group**
> remove_group(groupname=groupname, group_id=group_id, swap_group=swap_group, swap_group_id=swap_group_id)

Remove group

Deletes a group.  **[Permissions](#permissions) required:** Site administration (that is, member of the *site-admin* strategic [group](https://confluence.atlassian.com/x/24xjL)).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
groupname = 'groupname_example' # str |  (optional)
group_id = 'group_id_example' # str | The ID of the group. This parameter cannot be used with the `groupname` parameter. (optional)
swap_group = 'swap_group_example' # str | As a group's name can change, use of `swapGroupId` is recommended to identify a group.   The group to transfer restrictions to. Only comments and worklogs are transferred. If restrictions are not transferred, comments and worklogs are inaccessible after the deletion. This parameter cannot be used with the `swapGroupId` parameter. (optional)
swap_group_id = 'swap_group_id_example' # str | The ID of the group to transfer restrictions to. Only comments and worklogs are transferred. If restrictions are not transferred, comments and worklogs are inaccessible after the deletion. This parameter cannot be used with the `swapGroup` parameter. (optional)

try:
    # Remove group
    api_instance.remove_group(groupname=groupname, group_id=group_id, swap_group=swap_group, swap_group_id=swap_group_id)
except ApiException as e:
    print("Exception when calling GroupsApi->remove_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **groupname** | **str**|  | [optional] 
 **group_id** | **str**| The ID of the group. This parameter cannot be used with the &#x60;groupname&#x60; parameter. | [optional] 
 **swap_group** | **str**| As a group&#x27;s name can change, use of &#x60;swapGroupId&#x60; is recommended to identify a group.   The group to transfer restrictions to. Only comments and worklogs are transferred. If restrictions are not transferred, comments and worklogs are inaccessible after the deletion. This parameter cannot be used with the &#x60;swapGroupId&#x60; parameter. | [optional] 
 **swap_group_id** | **str**| The ID of the group to transfer restrictions to. Only comments and worklogs are transferred. If restrictions are not transferred, comments and worklogs are inaccessible after the deletion. This parameter cannot be used with the &#x60;swapGroup&#x60; parameter. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_user_from_group**
> remove_user_from_group(account_id, groupname=groupname, group_id=group_id, username=username)

Remove user from group

Removes a user from a group.  **[Permissions](#permissions) required:** Site administration (that is, member of the *site-admin* [group](https://confluence.atlassian.com/x/24xjL)).

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# Configure OAuth2 access token for authorization: OAuth2
configuration = jira_client.Configuration()
configuration.access_token = 'YOUR_ACCESS_TOKEN'# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.GroupsApi(jira_client.ApiClient(configuration))
account_id = 'account_id_example' # str | The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*.
groupname = 'groupname_example' # str | As a group's name can change, use of `groupId` is recommended to identify a group.   The name of the group. This parameter cannot be used with the `groupId` parameter. (optional)
group_id = 'group_id_example' # str | The ID of the group. This parameter cannot be used with the `groupName` parameter. (optional)
username = 'username_example' # str | This parameter is no longer available. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. (optional)

try:
    # Remove user from group
    api_instance.remove_user_from_group(account_id, groupname=groupname, group_id=group_id, username=username)
except ApiException as e:
    print("Exception when calling GroupsApi->remove_user_from_group: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **account_id** | **str**| The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. | 
 **groupname** | **str**| As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended to identify a group.   The name of the group. This parameter cannot be used with the &#x60;groupId&#x60; parameter. | [optional] 
 **group_id** | **str**| The ID of the group. This parameter cannot be used with the &#x60;groupName&#x60; parameter. | [optional] 
 **username** | **str**| This parameter is no longer available. See the [deprecation notice](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

