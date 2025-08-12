# jira_client.ProjectRoleActorsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_actor_users**](ProjectRoleActorsApi.md#add_actor_users) | **POST** /rest/api/3/project/{projectIdOrKey}/role/{id} | Add actors to project role
[**add_project_role_actors_to_role**](ProjectRoleActorsApi.md#add_project_role_actors_to_role) | **POST** /rest/api/3/role/{id}/actors | Add default actors to project role
[**delete_actor**](ProjectRoleActorsApi.md#delete_actor) | **DELETE** /rest/api/3/project/{projectIdOrKey}/role/{id} | Delete actors from project role
[**delete_project_role_actors_from_role**](ProjectRoleActorsApi.md#delete_project_role_actors_from_role) | **DELETE** /rest/api/3/role/{id}/actors | Delete default actors from project role
[**get_project_role_actors_for_role**](ProjectRoleActorsApi.md#get_project_role_actors_for_role) | **GET** /rest/api/3/role/{id}/actors | Get default actors for project role
[**set_actors**](ProjectRoleActorsApi.md#set_actors) | **PUT** /rest/api/3/project/{projectIdOrKey}/role/{id} | Set actors for project role

# **add_actor_users**
> ProjectRole add_actor_users(body, project_id_or_key, id)

Add actors to project role

Adds actors to a project role for the project.  To replace all actors for the project, use [Set actors for project role](#api-rest-api-3-project-projectIdOrKey-role-id-put).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
body = jira_client.ActorsMap() # ActorsMap | The groups or users to associate with the project role for this project. Provide the user account ID, group name, or group ID. As a group's name can change, use of group ID is recommended.
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case sensitive).
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.

try:
    # Add actors to project role
    api_response = api_instance.add_actor_users(body, project_id_or_key, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->add_actor_users: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ActorsMap**](ActorsMap.md)| The groups or users to associate with the project role for this project. Provide the user account ID, group name, or group ID. As a group&#x27;s name can change, use of group ID is recommended. | 
 **project_id_or_key** | **str**| The project ID or project key (case sensitive). | 
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 

### Return type

[**ProjectRole**](ProjectRole.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_project_role_actors_to_role**
> ProjectRole add_project_role_actors_to_role(body, id)

Add default actors to project role

Adds [default actors](#api-rest-api-3-resolution-get) to a role. You may add groups or users, but you cannot add groups and users in the same request.  Changing a project role's default actors does not affect project role members for projects already created.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
body = jira_client.ActorInputBean() # ActorInputBean | 
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.

try:
    # Add default actors to project role
    api_response = api_instance.add_project_role_actors_to_role(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->add_project_role_actors_to_role: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ActorInputBean**](ActorInputBean.md)|  | 
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 

### Return type

[**ProjectRole**](ProjectRole.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_actor**
> delete_actor(project_id_or_key, id, user=user, group=group, group_id=group_id)

Delete actors from project role

Deletes actors from a project role for the project.  To remove default actors from the project role, use [Delete default actors from project role](#api-rest-api-3-role-id-actors-delete).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case sensitive).
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.
user = 'user_example' # str | The user account ID of the user to remove from the project role. (optional)
group = 'group_example' # str | The name of the group to remove from the project role. This parameter cannot be used with the `groupId` parameter. As a group's name can change, use of `groupId` is recommended. (optional)
group_id = 'group_id_example' # str | The ID of the group to remove from the project role. This parameter cannot be used with the `group` parameter. (optional)

try:
    # Delete actors from project role
    api_instance.delete_actor(project_id_or_key, id, user=user, group=group, group_id=group_id)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->delete_actor: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or project key (case sensitive). | 
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 
 **user** | **str**| The user account ID of the user to remove from the project role. | [optional] 
 **group** | **str**| The name of the group to remove from the project role. This parameter cannot be used with the &#x60;groupId&#x60; parameter. As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended. | [optional] 
 **group_id** | **str**| The ID of the group to remove from the project role. This parameter cannot be used with the &#x60;group&#x60; parameter. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_project_role_actors_from_role**
> ProjectRole delete_project_role_actors_from_role(id, user=user, group_id=group_id, group=group)

Delete default actors from project role

Deletes the [default actors](#api-rest-api-3-resolution-get) from a project role. You may delete a group or user, but you cannot delete a group and a user in the same request.  Changing a project role's default actors does not affect project role members for projects already created.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.
user = 'user_example' # str | The user account ID of the user to remove as a default actor. (optional)
group_id = 'group_id_example' # str | The group ID of the group to be removed as a default actor. This parameter cannot be used with the `group` parameter. (optional)
group = 'group_example' # str | The group name of the group to be removed as a default actor.This parameter cannot be used with the `groupId` parameter. As a group's name can change, use of `groupId` is recommended. (optional)

try:
    # Delete default actors from project role
    api_response = api_instance.delete_project_role_actors_from_role(id, user=user, group_id=group_id, group=group)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->delete_project_role_actors_from_role: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 
 **user** | **str**| The user account ID of the user to remove as a default actor. | [optional] 
 **group_id** | **str**| The group ID of the group to be removed as a default actor. This parameter cannot be used with the &#x60;group&#x60; parameter. | [optional] 
 **group** | **str**| The group name of the group to be removed as a default actor.This parameter cannot be used with the &#x60;groupId&#x60; parameter. As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended. | [optional] 

### Return type

[**ProjectRole**](ProjectRole.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_role_actors_for_role**
> ProjectRole get_project_role_actors_for_role(id)

Get default actors for project role

Returns the [default actors](#api-rest-api-3-resolution-get) for the project role.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.

try:
    # Get default actors for project role
    api_response = api_instance.get_project_role_actors_for_role(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->get_project_role_actors_for_role: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 

### Return type

[**ProjectRole**](ProjectRole.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_actors**
> ProjectRole set_actors(body, project_id_or_key, id)

Set actors for project role

Sets the actors for a project role for a project, replacing all existing actors.  To add actors to the project without overwriting the existing list, use [Add actors to project role](#api-rest-api-3-project-projectIdOrKey-role-id-post).  **[Permissions](#permissions) required:** *Administer Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectRoleActorsApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectRoleActorsUpdateBean() # ProjectRoleActorsUpdateBean | The groups or users to associate with the project role for this project. Provide the user account ID, group name, or group ID. As a group's name can change, use of group ID is recommended.
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case sensitive).
id = 789 # int | The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs.

try:
    # Set actors for project role
    api_response = api_instance.set_actors(body, project_id_or_key, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectRoleActorsApi->set_actors: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectRoleActorsUpdateBean**](ProjectRoleActorsUpdateBean.md)| The groups or users to associate with the project role for this project. Provide the user account ID, group name, or group ID. As a group&#x27;s name can change, use of group ID is recommended. | 
 **project_id_or_key** | **str**| The project ID or project key (case sensitive). | 
 **id** | **int**| The ID of the project role. Use [Get all project roles](#api-rest-api-3-role-get) to get a list of project role IDs. | 

### Return type

[**ProjectRole**](ProjectRole.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

