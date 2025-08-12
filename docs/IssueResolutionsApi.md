# jira_client.IssueResolutionsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_resolution**](IssueResolutionsApi.md#create_resolution) | **POST** /rest/api/3/resolution | Create resolution
[**delete_resolution**](IssueResolutionsApi.md#delete_resolution) | **DELETE** /rest/api/3/resolution/{id} | Delete resolution
[**get_resolution**](IssueResolutionsApi.md#get_resolution) | **GET** /rest/api/3/resolution/{id} | Get resolution
[**get_resolutions**](IssueResolutionsApi.md#get_resolutions) | **GET** /rest/api/3/resolution | Get resolutions
[**move_resolutions**](IssueResolutionsApi.md#move_resolutions) | **PUT** /rest/api/3/resolution/move | Move resolutions
[**search_resolutions**](IssueResolutionsApi.md#search_resolutions) | **GET** /rest/api/3/resolution/search | Search resolutions
[**set_default_resolution**](IssueResolutionsApi.md#set_default_resolution) | **PUT** /rest/api/3/resolution/default | Set default resolution
[**update_resolution**](IssueResolutionsApi.md#update_resolution) | **PUT** /rest/api/3/resolution/{id} | Update resolution

# **create_resolution**
> ResolutionId create_resolution(body)

Create resolution

Creates an issue resolution.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My resolution description",
  "name" : "My new resolution"
} # dict(str, object) | 

try:
    # Create resolution
    api_response = api_instance.create_resolution(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->create_resolution: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

[**ResolutionId**](ResolutionId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_resolution**
> delete_resolution(id, replace_with)

Delete resolution

Deletes an issue resolution.  This operation is [asynchronous](#async). Follow the `location` link in the response to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain subsequent updates.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue resolution.
replace_with = '' # str | The ID of the issue resolution that will replace the currently selected resolution.

try:
    # Delete resolution
    api_instance.delete_resolution(id, replace_with)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->delete_resolution: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue resolution. | 
 **replace_with** | **str**| The ID of the issue resolution that will replace the currently selected resolution. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_resolution**
> Resolution get_resolution(id)

Get resolution

Returns an issue resolution value.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the issue resolution value.

try:
    # Get resolution
    api_response = api_instance.get_resolution(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->get_resolution: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the issue resolution value. | 

### Return type

[**Resolution**](Resolution.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_resolutions**
> list[Resolution] get_resolutions()

Get resolutions

Returns a list of all issue resolution values.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))

try:
    # Get resolutions
    api_response = api_instance.get_resolutions()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->get_resolutions: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[Resolution]**](Resolution.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_resolutions**
> object move_resolutions(body)

Move resolutions

Changes the order of issue resolutions.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
body = jira_client.ReorderIssueResolutionsRequest() # ReorderIssueResolutionsRequest | 

try:
    # Move resolutions
    api_response = api_instance.move_resolutions(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->move_resolutions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ReorderIssueResolutionsRequest**](ReorderIssueResolutionsRequest.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_resolutions**
> PageBeanResolutionJsonBean search_resolutions(start_at=start_at, max_results=max_results, id=id, only_default=only_default)

Search resolutions

Returns a [paginated](#pagination) list of resolutions. The list can contain all resolutions or a subset determined by any combination of these criteria:   *  a list of resolutions IDs.  *  whether the field configuration is a default. This returns resolutions from company-managed (classic) projects only, as there is no concept of default resolutions in team-managed projects.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of resolutions IDs to be filtered out (optional)
only_default = false # bool | When set to true, return default only, when IDs provided, if none of them is default, return empty page. Default value is false (optional) (default to false)

try:
    # Search resolutions
    api_response = api_instance.search_resolutions(start_at=start_at, max_results=max_results, id=id, only_default=only_default)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->search_resolutions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of resolutions IDs to be filtered out | [optional] 
 **only_default** | **bool**| When set to true, return default only, when IDs provided, if none of them is default, return empty page. Default value is false | [optional] [default to false]

### Return type

[**PageBeanResolutionJsonBean**](PageBeanResolutionJsonBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_default_resolution**
> object set_default_resolution(body)

Set default resolution

Sets default issue resolution.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
body = jira_client.SetDefaultResolutionRequest() # SetDefaultResolutionRequest | 

try:
    # Set default resolution
    api_response = api_instance.set_default_resolution(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->set_default_resolution: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SetDefaultResolutionRequest**](SetDefaultResolutionRequest.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_resolution**
> object update_resolution(body, id)

Update resolution

Updates an issue resolution.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueResolutionsApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My updated resolution description",
  "name" : "My updated resolution"
} # dict(str, object) | 
id = 'id_example' # str | The ID of the issue resolution.

try:
    # Update resolution
    api_response = api_instance.update_resolution(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueResolutionsApi->update_resolution: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **id** | **str**| The ID of the issue resolution. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

