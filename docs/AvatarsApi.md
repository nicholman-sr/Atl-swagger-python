# jira_client.AvatarsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_avatar**](AvatarsApi.md#delete_avatar) | **DELETE** /rest/api/3/universal_avatar/type/{type}/owner/{owningObjectId}/avatar/{id} | Delete avatar
[**get_all_system_avatars**](AvatarsApi.md#get_all_system_avatars) | **GET** /rest/api/3/avatar/{type}/system | Get system avatars by type
[**get_avatar_image_by_id**](AvatarsApi.md#get_avatar_image_by_id) | **GET** /rest/api/3/universal_avatar/view/type/{type}/avatar/{id} | Get avatar image by ID
[**get_avatar_image_by_owner**](AvatarsApi.md#get_avatar_image_by_owner) | **GET** /rest/api/3/universal_avatar/view/type/{type}/owner/{entityId} | Get avatar image by owner
[**get_avatar_image_by_type**](AvatarsApi.md#get_avatar_image_by_type) | **GET** /rest/api/3/universal_avatar/view/type/{type} | Get avatar image by type
[**get_avatars**](AvatarsApi.md#get_avatars) | **GET** /rest/api/3/universal_avatar/type/{type}/owner/{entityId} | Get avatars
[**store_avatar**](AvatarsApi.md#store_avatar) | **POST** /rest/api/3/universal_avatar/type/{type}/owner/{entityId} | Load avatar

# **delete_avatar**
> delete_avatar(type, owning_object_id, id)

Delete avatar

Deletes an avatar from a project, issue type or priority.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The avatar type.
owning_object_id = 'owning_object_id_example' # str | The ID of the item the avatar is associated with.
id = 789 # int | The ID of the avatar.

try:
    # Delete avatar
    api_instance.delete_avatar(type, owning_object_id, id)
except ApiException as e:
    print("Exception when calling AvatarsApi->delete_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The avatar type. | 
 **owning_object_id** | **str**| The ID of the item the avatar is associated with. | 
 **id** | **int**| The ID of the avatar. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_system_avatars**
> SystemAvatars get_all_system_avatars(type)

Get system avatars by type

Returns a list of system avatar details by owner type, where the owner types are issue type, project, user or priority.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The avatar type.

try:
    # Get system avatars by type
    api_response = api_instance.get_all_system_avatars(type)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AvatarsApi->get_all_system_avatars: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The avatar type. | 

### Return type

[**SystemAvatars**](SystemAvatars.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_avatar_image_by_id**
> get_avatar_image_by_id(type, id, size=size, format=format)

Get avatar image by ID

Returns a project, issue type or priority avatar image by ID.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  For system avatars, none.  *  For custom project avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project the avatar belongs to.  *  For custom issue type avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for at least one project the issue type is used in.  *  For priority avatars, none.

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The icon type of the avatar.
id = 789 # int | The ID of the avatar.
size = 'size_example' # str | The size of the avatar image. If not provided the default size is returned. (optional)
format = 'format_example' # str | The format to return the avatar image in. If not provided the original content format is returned. (optional)

try:
    # Get avatar image by ID
    api_instance.get_avatar_image_by_id(type, id, size=size, format=format)
except ApiException as e:
    print("Exception when calling AvatarsApi->get_avatar_image_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The icon type of the avatar. | 
 **id** | **int**| The ID of the avatar. | 
 **size** | **str**| The size of the avatar image. If not provided the default size is returned. | [optional] 
 **format** | **str**| The format to return the avatar image in. If not provided the original content format is returned. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*, application/json, image/png, image/svg+xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_avatar_image_by_owner**
> get_avatar_image_by_owner(type, entity_id, size=size, format=format)

Get avatar image by owner

Returns the avatar image for a project, issue type or priority.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  For system avatars, none.  *  For custom project avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project the avatar belongs to.  *  For custom issue type avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for at least one project the issue type is used in.  *  For priority avatars, none.

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The icon type of the avatar.
entity_id = 'entity_id_example' # str | The ID of the project or issue type the avatar belongs to.
size = 'size_example' # str | The size of the avatar image. If not provided the default size is returned. (optional)
format = 'format_example' # str | The format to return the avatar image in. If not provided the original content format is returned. (optional)

try:
    # Get avatar image by owner
    api_instance.get_avatar_image_by_owner(type, entity_id, size=size, format=format)
except ApiException as e:
    print("Exception when calling AvatarsApi->get_avatar_image_by_owner: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The icon type of the avatar. | 
 **entity_id** | **str**| The ID of the project or issue type the avatar belongs to. | 
 **size** | **str**| The size of the avatar image. If not provided the default size is returned. | [optional] 
 **format** | **str**| The format to return the avatar image in. If not provided the original content format is returned. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*, application/json, image/png, image/svg+xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_avatar_image_by_type**
> get_avatar_image_by_type(type, size=size, format=format)

Get avatar image by type

Returns the default project, issue type or priority avatar image.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The icon type of the avatar.
size = 'size_example' # str | The size of the avatar image. If not provided the default size is returned. (optional)
format = 'format_example' # str | The format to return the avatar image in. If not provided the original content format is returned. (optional)

try:
    # Get avatar image by type
    api_instance.get_avatar_image_by_type(type, size=size, format=format)
except ApiException as e:
    print("Exception when calling AvatarsApi->get_avatar_image_by_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The icon type of the avatar. | 
 **size** | **str**| The size of the avatar image. If not provided the default size is returned. | [optional] 
 **format** | **str**| The format to return the avatar image in. If not provided the original content format is returned. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: */*, application/json, image/png, image/svg+xml

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_avatars**
> Avatars get_avatars(type, entity_id)

Get avatars

Returns the system and custom avatars for a project, issue type or priority.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  for custom project avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project the avatar belongs to.  *  for custom issue type avatars, *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for at least one project the issue type is used in.  *  for system avatars, none.  *  for priority avatars, none.

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
type = 'type_example' # str | The avatar type.
entity_id = 'entity_id_example' # str | The ID of the item the avatar is associated with.

try:
    # Get avatars
    api_response = api_instance.get_avatars(type, entity_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AvatarsApi->get_avatars: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **type** | **str**| The avatar type. | 
 **entity_id** | **str**| The ID of the item the avatar is associated with. | 

### Return type

[**Avatars**](Avatars.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **store_avatar**
> Avatar store_avatar(body, size, type, entity_id, x=x, y=y)

Load avatar

Loads a custom avatar for a project, issue type or priority.  Specify the avatar's local file location in the body of the request. Also, include the following headers:   *  `X-Atlassian-Token: no-check` To prevent XSRF protection blocking the request, for more information see [Special Headers](#special-request-headers).  *  `Content-Type: image/image type` Valid image types are JPEG, GIF, or PNG.  For example:   `curl --request POST `  `--user email@example.com:<api_token> `  `--header 'X-Atlassian-Token: no-check' `  `--header 'Content-Type: image/< image_type>' `  `--data-binary \"<@/path/to/file/with/your/avatar>\" `  `--url 'https://your-domain.atlassian.net/rest/api/3/universal_avatar/type/{type}/owner/{entityId}'`  The avatar is cropped to a square. If no crop parameters are specified, the square originates at the top left of the image. The length of the square's sides is set to the smaller of the height or width of the image.  The cropped image is then used to create avatars of 16x16, 24x24, 32x32, and 48x48 in size.  After creating the avatar use:   *  [Update issue type](#api-rest-api-3-issuetype-id-put) to set it as the issue type's displayed avatar.  *  [Set project avatar](#api-rest-api-3-project-projectIdOrKey-avatar-put) to set it as the project's displayed avatar.  *  [Update priority](#api-rest-api-3-priority-id-put) to set it as the priority's displayed avatar.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.AvatarsApi(jira_client.ApiClient(configuration))
body = NULL # object | 
size = 0 # int | The length of each side of the crop region. (default to 0)
type = 'type_example' # str | The avatar type.
entity_id = 'entity_id_example' # str | The ID of the item the avatar is associated with.
x = 0 # int | The X coordinate of the top-left corner of the crop region. (optional) (default to 0)
y = 0 # int | The Y coordinate of the top-left corner of the crop region. (optional) (default to 0)

try:
    # Load avatar
    api_response = api_instance.store_avatar(body, size, type, entity_id, x=x, y=y)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AvatarsApi->store_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **size** | **int**| The length of each side of the crop region. | [default to 0]
 **type** | **str**| The avatar type. | 
 **entity_id** | **str**| The ID of the item the avatar is associated with. | 
 **x** | **int**| The X coordinate of the top-left corner of the crop region. | [optional] [default to 0]
 **y** | **int**| The Y coordinate of the top-left corner of the crop region. | [optional] [default to 0]

### Return type

[**Avatar**](Avatar.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: */*
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

