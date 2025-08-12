# jira_client.ProjectTypesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_accessible_project_type_by_key**](ProjectTypesApi.md#get_accessible_project_type_by_key) | **GET** /rest/api/3/project/type/{projectTypeKey}/accessible | Get accessible project type by key
[**get_all_accessible_project_types**](ProjectTypesApi.md#get_all_accessible_project_types) | **GET** /rest/api/3/project/type/accessible | Get licensed project types
[**get_all_project_types**](ProjectTypesApi.md#get_all_project_types) | **GET** /rest/api/3/project/type | Get all project types
[**get_project_type_by_key**](ProjectTypesApi.md#get_project_type_by_key) | **GET** /rest/api/3/project/type/{projectTypeKey} | Get project type by key

# **get_accessible_project_type_by_key**
> ProjectType get_accessible_project_type_by_key(project_type_key)

Get accessible project type by key

Returns a [project type](https://confluence.atlassian.com/x/Var1Nw) if it is accessible to the user.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.ProjectTypesApi(jira_client.ApiClient(configuration))
project_type_key = 'project_type_key_example' # str | The key of the project type.

try:
    # Get accessible project type by key
    api_response = api_instance.get_accessible_project_type_by_key(project_type_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTypesApi->get_accessible_project_type_by_key: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_type_key** | **str**| The key of the project type. | 

### Return type

[**ProjectType**](ProjectType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_accessible_project_types**
> list[ProjectType] get_all_accessible_project_types()

Get licensed project types

Returns all [project types](https://confluence.atlassian.com/x/Var1Nw) with a valid license.

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
api_instance = jira_client.ProjectTypesApi(jira_client.ApiClient(configuration))

try:
    # Get licensed project types
    api_response = api_instance.get_all_accessible_project_types()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTypesApi->get_all_accessible_project_types: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[ProjectType]**](ProjectType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_project_types**
> list[ProjectType] get_all_project_types()

Get all project types

Returns all [project types](https://confluence.atlassian.com/x/Var1Nw), whether or not the instance has a valid license for each type.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectTypesApi(jira_client.ApiClient(configuration))

try:
    # Get all project types
    api_response = api_instance.get_all_project_types()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTypesApi->get_all_project_types: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[ProjectType]**](ProjectType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_type_by_key**
> ProjectType get_project_type_by_key(project_type_key)

Get project type by key

Returns a [project type](https://confluence.atlassian.com/x/Var1Nw).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectTypesApi(jira_client.ApiClient(configuration))
project_type_key = 'project_type_key_example' # str | The key of the project type.

try:
    # Get project type by key
    api_response = api_instance.get_project_type_by_key(project_type_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTypesApi->get_project_type_by_key: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_type_key** | **str**| The key of the project type. | 

### Return type

[**ProjectType**](ProjectType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

