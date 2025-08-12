# jira_client.AppDataPoliciesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_policies**](AppDataPoliciesApi.md#get_policies) | **GET** /rest/api/3/data-policy/project | Get data policy for projects
[**get_policy**](AppDataPoliciesApi.md#get_policy) | **GET** /rest/api/3/data-policy | Get data policy for the workspace

# **get_policies**
> ProjectDataPolicies get_policies(ids=ids)

Get data policy for projects

Returns data policies for the projects specified in the request.

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
api_instance = jira_client.AppDataPoliciesApi(jira_client.ApiClient(configuration))
ids = 'ids_example' # str | A list of project identifiers. This parameter accepts a comma-separated list. (optional)

try:
    # Get data policy for projects
    api_response = api_instance.get_policies(ids=ids)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AppDataPoliciesApi->get_policies: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ids** | **str**| A list of project identifiers. This parameter accepts a comma-separated list. | [optional] 

### Return type

[**ProjectDataPolicies**](ProjectDataPolicies.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_policy**
> WorkspaceDataPolicy get_policy()

Get data policy for the workspace

Returns data policy for the workspace.

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
api_instance = jira_client.AppDataPoliciesApi(jira_client.ApiClient(configuration))

try:
    # Get data policy for the workspace
    api_response = api_instance.get_policy()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AppDataPoliciesApi->get_policy: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**WorkspaceDataPolicy**](WorkspaceDataPolicy.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

