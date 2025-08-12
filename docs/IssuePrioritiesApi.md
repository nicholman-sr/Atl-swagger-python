# jira_client.IssuePrioritiesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_priority**](IssuePrioritiesApi.md#create_priority) | **POST** /rest/api/3/priority | Create priority
[**delete_priority**](IssuePrioritiesApi.md#delete_priority) | **DELETE** /rest/api/3/priority/{id} | Delete priority
[**get_priorities**](IssuePrioritiesApi.md#get_priorities) | **GET** /rest/api/3/priority | Get priorities
[**get_priority**](IssuePrioritiesApi.md#get_priority) | **GET** /rest/api/3/priority/{id} | Get priority
[**move_priorities**](IssuePrioritiesApi.md#move_priorities) | **PUT** /rest/api/3/priority/move | Move priorities
[**search_priorities**](IssuePrioritiesApi.md#search_priorities) | **GET** /rest/api/3/priority/search | Search priorities
[**set_default_priority**](IssuePrioritiesApi.md#set_default_priority) | **PUT** /rest/api/3/priority/default | Set default priority
[**update_priority**](IssuePrioritiesApi.md#update_priority) | **PUT** /rest/api/3/priority/{id} | Update priority

# **create_priority**
> PriorityId create_priority(body)

Create priority

Creates an issue priority.  Deprecation applies to iconUrl param in request body which will be sunset on 16th Mar 2025. For more details refer to [changelog](https://developer.atlassian.com/changelog/#CHANGE-1525).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My priority description",
  "iconUrl" : "images/icons/priorities/major.png",
  "name" : "My new priority",
  "statusColor" : "#ABCDEF"
} # dict(str, object) | 

try:
    # Create priority
    api_response = api_instance.create_priority(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->create_priority: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

[**PriorityId**](PriorityId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_priority**
> delete_priority(id)

Delete priority

Deletes an issue priority.  This operation is [asynchronous](#async). Follow the `location` link in the response to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain subsequent updates.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue priority.

try:
    # Delete priority
    api_instance.delete_priority(id)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->delete_priority: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue priority. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_priorities**
> list[Priority] get_priorities()

Get priorities

Returns the list of all issue priorities.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))

try:
    # Get priorities
    api_response = api_instance.get_priorities()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->get_priorities: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[Priority]**](Priority.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_priority**
> Priority get_priority(id)

Get priority

Returns an issue priority.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue priority.

try:
    # Get priority
    api_response = api_instance.get_priority(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->get_priority: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue priority. | 

### Return type

[**Priority**](Priority.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_priorities**
> object move_priorities(body)

Move priorities

Changes the order of issue priorities.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
body = jira_client.ReorderIssuePriorities() # ReorderIssuePriorities | 

try:
    # Move priorities
    api_response = api_instance.move_priorities(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->move_priorities: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ReorderIssuePriorities**](ReorderIssuePriorities.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_priorities**
> PageBeanPriority search_priorities(start_at=start_at, max_results=max_results, id=id, project_id=project_id, priority_name=priority_name, only_default=only_default, expand=expand)

Search priorities

Returns a [paginated](#pagination) list of priorities. The list can contain all priorities or a subset determined by any combination of these criteria:   *  a list of priority IDs. Any invalid priority IDs are ignored.  *  a list of project IDs. Only priorities that are available in these projects will be returned. Any invalid project IDs are ignored.  *  whether the field configuration is a default. This returns priorities from company-managed (classic) projects only, as there is no concept of default priorities in team-managed projects.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of priority IDs. To include multiple IDs, provide an ampersand-separated list. For example, `id=2&id=3`. (optional)
project_id = ['project_id_example'] # list[str] | The list of projects IDs. To include multiple IDs, provide an ampersand-separated list. For example, `projectId=10010&projectId=10111`. (optional)
priority_name = '' # str | The name of priority to search for. (optional)
only_default = false # bool | Whether only the default priority is returned. (optional) (default to false)
expand = '' # str | Use `schemes` to return the associated priority schemes for each priority. Limited to returning first 15 priority schemes per priority. (optional)

try:
    # Search priorities
    api_response = api_instance.search_priorities(start_at=start_at, max_results=max_results, id=id, project_id=project_id, priority_name=priority_name, only_default=only_default, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->search_priorities: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of priority IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;id&#x3D;2&amp;id&#x3D;3&#x60;. | [optional] 
 **project_id** | [**list[str]**](str.md)| The list of projects IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;projectId&#x3D;10010&amp;projectId&#x3D;10111&#x60;. | [optional] 
 **priority_name** | **str**| The name of priority to search for. | [optional] 
 **only_default** | **bool**| Whether only the default priority is returned. | [optional] [default to false]
 **expand** | **str**| Use &#x60;schemes&#x60; to return the associated priority schemes for each priority. Limited to returning first 15 priority schemes per priority. | [optional] 

### Return type

[**PageBeanPriority**](PageBeanPriority.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_default_priority**
> object set_default_priority(body)

Set default priority

Sets default issue priority.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
body = jira_client.SetDefaultPriorityRequest() # SetDefaultPriorityRequest | 

try:
    # Set default priority
    api_response = api_instance.set_default_priority(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->set_default_priority: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SetDefaultPriorityRequest**](SetDefaultPriorityRequest.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_priority**
> object update_priority(body, id)

Update priority

Updates an issue priority.  At least one request body parameter must be defined.  Deprecation applies to iconUrl param in request body which will be sunset on 16th Mar 2025. For more details refer to [changelog](https://developer.atlassian.com/changelog/#CHANGE-1525).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuePrioritiesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My updated priority description",
  "iconUrl" : "images/icons/priorities/minor.png",
  "name" : "My updated priority",
  "statusColor" : "#123456"
} # dict(str, object) | 
id = 'id_example' # str | The ID of the issue priority.

try:
    # Update priority
    api_response = api_instance.update_priority(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuePrioritiesApi->update_priority: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **id** | **str**| The ID of the issue priority. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

