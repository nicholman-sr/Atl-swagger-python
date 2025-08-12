# jira_client.WorkflowStatusesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_status**](WorkflowStatusesApi.md#get_status) | **GET** /rest/api/3/status/{idOrName} | Get status
[**get_statuses**](WorkflowStatusesApi.md#get_statuses) | **GET** /rest/api/3/status | Get all statuses

# **get_status**
> StatusDetails get_status(id_or_name)

Get status

Returns a status. The status must be associated with an active workflow to be returned.  If a name is used on more than one status, only the status found first is returned. Therefore, identifying the status by its ID may be preferable.  This operation can be accessed anonymously.  [Permissions](#permissions) required: *Browse projects* [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) for the project.

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
api_instance = jira_client.WorkflowStatusesApi(jira_client.ApiClient(configuration))
id_or_name = 'id_or_name_example' # str | The ID or name of the status.

try:
    # Get status
    api_response = api_instance.get_status(id_or_name)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowStatusesApi->get_status: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id_or_name** | **str**| The ID or name of the status. | 

### Return type

[**StatusDetails**](StatusDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_statuses**
> list[StatusDetails] get_statuses()

Get all statuses

Returns a list of all statuses associated with active workflows.  This operation can be accessed anonymously.  [Permissions](#permissions) required: *Browse projects* [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) for the project.

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
api_instance = jira_client.WorkflowStatusesApi(jira_client.ApiClient(configuration))

try:
    # Get all statuses
    api_response = api_instance.get_statuses()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowStatusesApi->get_statuses: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[StatusDetails]**](StatusDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

