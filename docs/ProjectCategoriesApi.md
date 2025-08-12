# jira_client.ProjectCategoriesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_project_category**](ProjectCategoriesApi.md#create_project_category) | **POST** /rest/api/3/projectCategory | Create project category
[**get_all_project_categories**](ProjectCategoriesApi.md#get_all_project_categories) | **GET** /rest/api/3/projectCategory | Get all project categories
[**get_project_category_by_id**](ProjectCategoriesApi.md#get_project_category_by_id) | **GET** /rest/api/3/projectCategory/{id} | Get project category by ID
[**remove_project_category**](ProjectCategoriesApi.md#remove_project_category) | **DELETE** /rest/api/3/projectCategory/{id} | Delete project category
[**update_project_category**](ProjectCategoriesApi.md#update_project_category) | **PUT** /rest/api/3/projectCategory/{id} | Update project category

# **create_project_category**
> ProjectCategory create_project_category(body)

Create project category

Creates a project category.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectCategoriesApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectCategory() # ProjectCategory | 

try:
    # Create project category
    api_response = api_instance.create_project_category(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectCategoriesApi->create_project_category: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectCategory**](ProjectCategory.md)|  | 

### Return type

[**ProjectCategory**](ProjectCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_project_categories**
> list[ProjectCategory] get_all_project_categories()

Get all project categories

Returns all project categories.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.ProjectCategoriesApi(jira_client.ApiClient(configuration))

try:
    # Get all project categories
    api_response = api_instance.get_all_project_categories()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectCategoriesApi->get_all_project_categories: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[ProjectCategory]**](ProjectCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_category_by_id**
> ProjectCategory get_project_category_by_id(id)

Get project category by ID

Returns a project category.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.ProjectCategoriesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the project category.

try:
    # Get project category by ID
    api_response = api_instance.get_project_category_by_id(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectCategoriesApi->get_project_category_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the project category. | 

### Return type

[**ProjectCategory**](ProjectCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_project_category**
> remove_project_category(id)

Delete project category

Deletes a project category.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectCategoriesApi(jira_client.ApiClient(configuration))
id = 789 # int | ID of the project category to delete.

try:
    # Delete project category
    api_instance.remove_project_category(id)
except ApiException as e:
    print("Exception when calling ProjectCategoriesApi->remove_project_category: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| ID of the project category to delete. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_project_category**
> UpdatedProjectCategory update_project_category(body, id)

Update project category

Updates a project category.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectCategoriesApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectCategory() # ProjectCategory | 
id = 789 # int | 

try:
    # Update project category
    api_response = api_instance.update_project_category(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectCategoriesApi->update_project_category: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectCategory**](ProjectCategory.md)|  | 
 **id** | **int**|  | 

### Return type

[**UpdatedProjectCategory**](UpdatedProjectCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

