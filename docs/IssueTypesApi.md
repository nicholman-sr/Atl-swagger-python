# jira_client.IssueTypesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_issue_type**](IssueTypesApi.md#create_issue_type) | **POST** /rest/api/3/issuetype | Create issue type
[**create_issue_type_avatar**](IssueTypesApi.md#create_issue_type_avatar) | **POST** /rest/api/3/issuetype/{id}/avatar2 | Load issue type avatar
[**delete_issue_type**](IssueTypesApi.md#delete_issue_type) | **DELETE** /rest/api/3/issuetype/{id} | Delete issue type
[**get_alternative_issue_types**](IssueTypesApi.md#get_alternative_issue_types) | **GET** /rest/api/3/issuetype/{id}/alternatives | Get alternative issue types
[**get_issue_all_types**](IssueTypesApi.md#get_issue_all_types) | **GET** /rest/api/3/issuetype | Get all issue types for user
[**get_issue_type**](IssueTypesApi.md#get_issue_type) | **GET** /rest/api/3/issuetype/{id} | Get issue type
[**get_issue_types_for_project**](IssueTypesApi.md#get_issue_types_for_project) | **GET** /rest/api/3/issuetype/project | Get issue types for project
[**update_issue_type**](IssueTypesApi.md#update_issue_type) | **PUT** /rest/api/3/issuetype/{id} | Update issue type

# **create_issue_type**
> IssueTypeDetails create_issue_type(body)

Create issue type

Creates an issue type and adds it to the default issue type scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeCreateBean() # IssueTypeCreateBean | 

try:
    # Create issue type
    api_response = api_instance.create_issue_type(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->create_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeCreateBean**](IssueTypeCreateBean.md)|  | 

### Return type

[**IssueTypeDetails**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issue_type_avatar**
> Avatar create_issue_type_avatar(body, size, id, x=x, y=y)

Load issue type avatar

Loads an avatar for the issue type.  Specify the avatar's local file location in the body of the request. Also, include the following headers:   *  `X-Atlassian-Token: no-check` To prevent XSRF protection blocking the request, for more information see [Special Headers](#special-request-headers).  *  `Content-Type: image/image type` Valid image types are JPEG, GIF, or PNG.  For example:   `curl --request POST \\ --user email@example.com:<api_token> \\ --header 'X-Atlassian-Token: no-check' \\ --header 'Content-Type: image/< image_type>' \\ --data-binary \"<@/path/to/file/with/your/avatar>\" \\ --url 'https://your-domain.atlassian.net/rest/api/3/issuetype/{issueTypeId}'This`  The avatar is cropped to a square. If no crop parameters are specified, the square originates at the top left of the image. The length of the square's sides is set to the smaller of the height or width of the image.  The cropped image is then used to create avatars of 16x16, 24x24, 32x32, and 48x48 in size.  After creating the avatar, use [ Update issue type](#api-rest-api-3-issuetype-id-put) to set it as the issue type's displayed avatar.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
body = NULL # object | 
size = 56 # int | The length of each side of the crop region.
id = 'id_example' # str | The ID of the issue type.
x = 0 # int | The X coordinate of the top-left corner of the crop region. (optional) (default to 0)
y = 0 # int | The Y coordinate of the top-left corner of the crop region. (optional) (default to 0)

try:
    # Load issue type avatar
    api_response = api_instance.create_issue_type_avatar(body, size, id, x=x, y=y)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->create_issue_type_avatar: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **size** | **int**| The length of each side of the crop region. | 
 **id** | **str**| The ID of the issue type. | 
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

# **delete_issue_type**
> delete_issue_type(id, alternative_issue_type_id=alternative_issue_type_id)

Delete issue type

Deletes the issue type. If the issue type is in use, all uses are updated with the alternative issue type (`alternativeIssueTypeId`). A list of alternative issue types are obtained from the [Get alternative issue types](#api-rest-api-3-issuetype-id-alternatives-get) resource.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue type.
alternative_issue_type_id = 'alternative_issue_type_id_example' # str | The ID of the replacement issue type. (optional)

try:
    # Delete issue type
    api_instance.delete_issue_type(id, alternative_issue_type_id=alternative_issue_type_id)
except ApiException as e:
    print("Exception when calling IssueTypesApi->delete_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue type. | 
 **alternative_issue_type_id** | **str**| The ID of the replacement issue type. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_alternative_issue_types**
> list[IssueTypeDetails] get_alternative_issue_types(id)

Get alternative issue types

Returns a list of issue types that can be used to replace the issue type. The alternative issue types are those assigned to the same workflow scheme, field configuration scheme, and screen scheme.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue type.

try:
    # Get alternative issue types
    api_response = api_instance.get_alternative_issue_types(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->get_alternative_issue_types: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue type. | 

### Return type

[**list[IssueTypeDetails]**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_all_types**
> list[IssueTypeDetails] get_issue_all_types()

Get all issue types for user

Returns all issue types.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issue types are only returned as follows:   *  if the user has the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), all issue types are returned.  *  if the user has the *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for one or more projects, the issue types associated with the projects the user has permission to browse are returned.  *  if the user is anonymous then they will be able to access projects with the *Browse projects* for anonymous users  *  if the user authentication is incorrect they will fall back to anonymous

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))

try:
    # Get all issue types for user
    api_response = api_instance.get_issue_all_types()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->get_issue_all_types: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[IssueTypeDetails]**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type**
> IssueTypeDetails get_issue_type(id)

Get issue type

Returns an issue type.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) in a project the issue type is associated with or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue type.

try:
    # Get issue type
    api_response = api_instance.get_issue_type(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->get_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue type. | 

### Return type

[**IssueTypeDetails**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_types_for_project**
> list[IssueTypeDetails] get_issue_types_for_project(project_id, level=level)

Get issue types for project

Returns issue types for a project.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) in the relevant project or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
project_id = 789 # int | The ID of the project.
level = 56 # int | The level of the issue type to filter by. Use:   *  `-1` for Subtask.  *  `0` for Base.  *  `1` for Epic. (optional)

try:
    # Get issue types for project
    api_response = api_instance.get_issue_types_for_project(project_id, level=level)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->get_issue_types_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | **int**| The ID of the project. | 
 **level** | **int**| The level of the issue type to filter by. Use:   *  &#x60;-1&#x60; for Subtask.  *  &#x60;0&#x60; for Base.  *  &#x60;1&#x60; for Epic. | [optional] 

### Return type

[**list[IssueTypeDetails]**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_issue_type**
> IssueTypeDetails update_issue_type(body, id)

Update issue type

Updates the issue type.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeUpdateBean() # IssueTypeUpdateBean | 
id = 'id_example' # str | The ID of the issue type.

try:
    # Update issue type
    api_response = api_instance.update_issue_type(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypesApi->update_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeUpdateBean**](IssueTypeUpdateBean.md)|  | 
 **id** | **str**| The ID of the issue type. | 

### Return type

[**IssueTypeDetails**](IssueTypeDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

