# jira_client.ProjectClassificationLevelsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_default_project_classification**](ProjectClassificationLevelsApi.md#get_default_project_classification) | **GET** /rest/api/3/project/{projectIdOrKey}/classification-level/default | Get the default data classification level of a project
[**remove_default_project_classification**](ProjectClassificationLevelsApi.md#remove_default_project_classification) | **DELETE** /rest/api/3/project/{projectIdOrKey}/classification-level/default | Remove the default data classification level from a project
[**update_default_project_classification**](ProjectClassificationLevelsApi.md#update_default_project_classification) | **PUT** /rest/api/3/project/{projectIdOrKey}/classification-level/default | Update the default data classification level of a project

# **get_default_project_classification**
> object get_default_project_classification(project_id_or_key)

Get the default data classification level of a project

Returns the default data classification for a project.  **[Permissions](#permissions) required:**   *  *Browse Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.  *  *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.  *  *Administer jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectClassificationLevelsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case-sensitive).

try:
    # Get the default data classification level of a project
    api_response = api_instance.get_default_project_classification(project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectClassificationLevelsApi->get_default_project_classification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or project key (case-sensitive). | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_default_project_classification**
> object remove_default_project_classification(project_id_or_key)

Remove the default data classification level from a project

Remove the default data classification level for a project.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.  *  *Administer jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectClassificationLevelsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case-sensitive).

try:
    # Remove the default data classification level from a project
    api_response = api_instance.remove_default_project_classification(project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectClassificationLevelsApi->remove_default_project_classification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or project key (case-sensitive). | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_default_project_classification**
> object update_default_project_classification(body, project_id_or_key)

Update the default data classification level of a project

Updates the default data classification level for a project.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.  *  *Administer jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectClassificationLevelsApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateDefaultProjectClassificationBean() # UpdateDefaultProjectClassificationBean | 
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case-sensitive).

try:
    # Update the default data classification level of a project
    api_response = api_instance.update_default_project_classification(body, project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectClassificationLevelsApi->update_default_project_classification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateDefaultProjectClassificationBean**](UpdateDefaultProjectClassificationBean.md)|  | 
 **project_id_or_key** | **str**| The project ID or project key (case-sensitive). | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

