# jira_client.ProjectEmailApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_project_email**](ProjectEmailApi.md#get_project_email) | **GET** /rest/api/3/project/{projectId}/email | Get project&#x27;s sender email
[**update_project_email**](ProjectEmailApi.md#update_project_email) | **PUT** /rest/api/3/project/{projectId}/email | Set project&#x27;s sender email

# **get_project_email**
> ProjectEmailAddress get_project_email(project_id)

Get project's sender email

Returns the [project's sender email address](https://confluence.atlassian.com/x/dolKLg).  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.

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
api_instance = jira_client.ProjectEmailApi(jira_client.ApiClient(configuration))
project_id = 789 # int | The project ID.

try:
    # Get project's sender email
    api_response = api_instance.get_project_email(project_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectEmailApi->get_project_email: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | **int**| The project ID. | 

### Return type

[**ProjectEmailAddress**](ProjectEmailAddress.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_project_email**
> object update_project_email(body, project_id)

Set project's sender email

Sets the [project's sender email address](https://confluence.atlassian.com/x/dolKLg).  If `emailAddress` is an empty string, the default email address is restored.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) or *Administer Projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.ProjectEmailApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectEmailAddress() # ProjectEmailAddress | The project's sender email address to be set.
project_id = 789 # int | The project ID.

try:
    # Set project's sender email
    api_response = api_instance.update_project_email(body, project_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectEmailApi->update_project_email: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectEmailAddress**](ProjectEmailAddress.md)| The project&#x27;s sender email address to be set. | 
 **project_id** | **int**| The project ID. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

