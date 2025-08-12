# jira_client.ProjectAvatarsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_project_avatar**](ProjectAvatarsApi.md#create_project_avatar) | **POST** /rest/api/3/project/{projectIdOrKey}/avatar2 | Load project avatar
[**delete_project_avatar**](ProjectAvatarsApi.md#delete_project_avatar) | **DELETE** /rest/api/3/project/{projectIdOrKey}/avatar/{id} | Delete project avatar
[**get_all_project_avatars**](ProjectAvatarsApi.md#get_all_project_avatars) | **GET** /rest/api/3/project/{projectIdOrKey}/avatars | Get all project avatars
[**update_project_avatar**](ProjectAvatarsApi.md#update_project_avatar) | **PUT** /rest/api/3/project/{projectIdOrKey}/avatar | Set project avatar

# **create_project_avatar**
> Avatar create_project_avatar(body, project_id_or_key, x=x, y=y, size=size)

Load project avatar

Loads an avatar for a project.  Specify the avatar's local file location in the body of the request. Also, include the following headers:   *  `X-Atlassian-Token: no-check` To prevent XSRF protection blocking the request, for more information see [Special Headers](#special-request-headers).  *  `Content-Type: image/image type` Valid image types are JPEG, GIF, or PNG.  For example:   `curl --request POST `  `--user email@example.com:<api_token> `  `--header 'X-Atlassian-Token: no-check' `  `--header 'Content-Type: image/< image_type>' `  `--data-binary \"<@/path/to/file/with/your/avatar>\" `  `--url 'https://your-domain.atlassian.net/rest/api/3/project/{projectIdOrKey}/avatar2'`  The avatar is cropped to a square. If no crop parameters are specified, the square originates at the top left of the image. The length of the square's sides is set to the smaller of the height or width of the image.  The cropped image is then used to create avatars of 16x16, 24x24, 32x32, and 48x48 in size.  After creating the avatar use [Set project avatar](#api-rest-api-3-project-projectIdOrKey-avatar-put) to set it as the project's displayed avatar.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg).

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
api_instance = jira_client.ProjectAvatarsApi(jira_client.ApiClient(configuration))
body = NULL # object | 
project_id_or_key = 'project_id_or_key_example' # str | The ID or (case-sensitive) key of the project.
x = 0 # int | The X coordinate of the top-left corner of the crop region. (optional) (default to 0)
y = 0 # int | The Y coordinate of the top-left corner of the crop region. (optional) (default to 0)
size = 0 # int | The length of each side of the crop region. (optional) (default to 0)

try:
    # Load project avatar
    api_response = api_instance.create_project_avatar(body, project_id_or_key, x=x, y=y, size=size)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectAvatarsApi->create_project_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **project_id_or_key** | **str**| The ID or (case-sensitive) key of the project. | 
 **x** | **int**| The X coordinate of the top-left corner of the crop region. | [optional] [default to 0]
 **y** | **int**| The Y coordinate of the top-left corner of the crop region. | [optional] [default to 0]
 **size** | **int**| The length of each side of the crop region. | [optional] [default to 0]

### Return type

[**Avatar**](Avatar.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_project_avatar**
> delete_project_avatar(project_id_or_key, id)

Delete project avatar

Deletes a custom avatar from a project. Note that system avatars cannot be deleted.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg).

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
api_instance = jira_client.ProjectAvatarsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or (case-sensitive) key.
id = 789 # int | The ID of the avatar.

try:
    # Delete project avatar
    api_instance.delete_project_avatar(project_id_or_key, id)
except ApiException as e:
    print("Exception when calling ProjectAvatarsApi->delete_project_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or (case-sensitive) key. | 
 **id** | **int**| The ID of the avatar. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_project_avatars**
> ProjectAvatars get_all_project_avatars(project_id_or_key)

Get all project avatars

Returns all project avatars, grouped by system and custom avatars.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.

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
api_instance = jira_client.ProjectAvatarsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The ID or (case-sensitive) key of the project.

try:
    # Get all project avatars
    api_response = api_instance.get_all_project_avatars(project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectAvatarsApi->get_all_project_avatars: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The ID or (case-sensitive) key of the project. | 

### Return type

[**ProjectAvatars**](ProjectAvatars.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_project_avatar**
> object update_project_avatar(body, project_id_or_key)

Set project avatar

Sets the avatar displayed for a project.  Use [Load project avatar](#api-rest-api-3-project-projectIdOrKey-avatar2-post) to store avatars against the project, before using this operation to set the displayed avatar.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg).

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
api_instance = jira_client.ProjectAvatarsApi(jira_client.ApiClient(configuration))
body = {
  "id" : "10010"
} # dict(str, object) | 
project_id_or_key = 'project_id_or_key_example' # str | The ID or (case-sensitive) key of the project.

try:
    # Set project avatar
    api_response = api_instance.update_project_avatar(body, project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectAvatarsApi->update_project_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **project_id_or_key** | **str**| The ID or (case-sensitive) key of the project. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

