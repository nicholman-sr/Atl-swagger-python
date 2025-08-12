# jira_client.WorkflowStatusCategoriesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_status_categories**](WorkflowStatusCategoriesApi.md#get_status_categories) | **GET** /rest/api/3/statuscategory | Get all status categories
[**get_status_category**](WorkflowStatusCategoriesApi.md#get_status_category) | **GET** /rest/api/3/statuscategory/{idOrKey} | Get status category

# **get_status_categories**
> list[StatusCategory] get_status_categories()

Get all status categories

Returns a list of all status categories.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.WorkflowStatusCategoriesApi(jira_client.ApiClient(configuration))

try:
    # Get all status categories
    api_response = api_instance.get_status_categories()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowStatusCategoriesApi->get_status_categories: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[StatusCategory]**](StatusCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_status_category**
> StatusCategory get_status_category(id_or_key)

Get status category

Returns a status category. Status categories provided a mechanism for categorizing [statuses](#api-rest-api-3-status-idOrName-get).  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.WorkflowStatusCategoriesApi(jira_client.ApiClient(configuration))
id_or_key = 'id_or_key_example' # str | The ID or key of the status category.

try:
    # Get status category
    api_response = api_instance.get_status_category(id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowStatusCategoriesApi->get_status_category: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id_or_key** | **str**| The ID or key of the status category. | 

### Return type

[**StatusCategory**](StatusCategory.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

