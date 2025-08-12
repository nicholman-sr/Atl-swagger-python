# jira_client.ClassificationLevelsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_all_user_data_classification_levels**](ClassificationLevelsApi.md#get_all_user_data_classification_levels) | **GET** /rest/api/3/classification-levels | Get all classification levels

# **get_all_user_data_classification_levels**
> DataClassificationLevelsBean get_all_user_data_classification_levels(status=status, order_by=order_by)

Get all classification levels

Returns all classification levels.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ClassificationLevelsApi(jira_client.ApiClient(configuration))
status = ['status_example'] # list[str] | Optional set of statuses to filter by. (optional)
order_by = 'order_by_example' # str | Ordering of the results by a given field. If not provided, values will not be sorted. (optional)

try:
    # Get all classification levels
    api_response = api_instance.get_all_user_data_classification_levels(status=status, order_by=order_by)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ClassificationLevelsApi->get_all_user_data_classification_levels: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status** | [**list[str]**](str.md)| Optional set of statuses to filter by. | [optional] 
 **order_by** | **str**| Ordering of the results by a given field. If not provided, values will not be sorted. | [optional] 

### Return type

[**DataClassificationLevelsBean**](DataClassificationLevelsBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

