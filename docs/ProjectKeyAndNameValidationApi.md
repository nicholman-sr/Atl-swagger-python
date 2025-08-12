# jira_client.ProjectKeyAndNameValidationApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_valid_project_key**](ProjectKeyAndNameValidationApi.md#get_valid_project_key) | **GET** /rest/api/3/projectvalidate/validProjectKey | Get valid project key
[**get_valid_project_name**](ProjectKeyAndNameValidationApi.md#get_valid_project_name) | **GET** /rest/api/3/projectvalidate/validProjectName | Get valid project name
[**validate_project_key**](ProjectKeyAndNameValidationApi.md#validate_project_key) | **GET** /rest/api/3/projectvalidate/key | Validate project key

# **get_valid_project_key**
> str get_valid_project_key(key=key)

Get valid project key

Validates a project key and, if the key is invalid or in use, generates a valid random string for the project key.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectKeyAndNameValidationApi(jira_client.ApiClient(configuration))
key = 'key_example' # str | The project key. (optional)

try:
    # Get valid project key
    api_response = api_instance.get_valid_project_key(key=key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectKeyAndNameValidationApi->get_valid_project_key: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key** | **str**| The project key. | [optional] 

### Return type

**str**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_valid_project_name**
> str get_valid_project_name(name)

Get valid project name

Checks that a project name isn't in use. If the name isn't in use, the passed string is returned. If the name is in use, this operation attempts to generate a valid project name based on the one supplied, usually by adding a sequence number. If a valid project name cannot be generated, a 404 response is returned.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectKeyAndNameValidationApi(jira_client.ApiClient(configuration))
name = 'name_example' # str | The project name.

try:
    # Get valid project name
    api_response = api_instance.get_valid_project_name(name)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectKeyAndNameValidationApi->get_valid_project_name: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **name** | **str**| The project name. | 

### Return type

**str**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **validate_project_key**
> ErrorCollection validate_project_key(key=key)

Validate project key

Validates a project key by confirming the key is a valid string and not in use.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectKeyAndNameValidationApi(jira_client.ApiClient(configuration))
key = 'key_example' # str | The project key. (optional)

try:
    # Validate project key
    api_response = api_instance.validate_project_key(key=key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectKeyAndNameValidationApi->validate_project_key: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key** | **str**| The project key. | [optional] 

### Return type

[**ErrorCollection**](ErrorCollection.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

