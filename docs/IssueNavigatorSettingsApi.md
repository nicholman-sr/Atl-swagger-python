# jira_client.IssueNavigatorSettingsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_issue_navigator_default_columns**](IssueNavigatorSettingsApi.md#get_issue_navigator_default_columns) | **GET** /rest/api/3/settings/columns | Get issue navigator default columns
[**set_issue_navigator_default_columns**](IssueNavigatorSettingsApi.md#set_issue_navigator_default_columns) | **PUT** /rest/api/3/settings/columns | Set issue navigator default columns

# **get_issue_navigator_default_columns**
> list[ColumnItem] get_issue_navigator_default_columns()

Get issue navigator default columns

Returns the default issue navigator columns.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNavigatorSettingsApi(jira_client.ApiClient(configuration))

try:
    # Get issue navigator default columns
    api_response = api_instance.get_issue_navigator_default_columns()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNavigatorSettingsApi->get_issue_navigator_default_columns: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[ColumnItem]**](ColumnItem.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_issue_navigator_default_columns**
> set_issue_navigator_default_columns(body)

Set issue navigator default columns

Sets the default issue navigator columns.  The `columns` parameter accepts a navigable field value and is expressed as HTML form data. To specify multiple columns, pass multiple `columns` parameters. For example, in curl:  `curl -X PUT -d columns=summary -d columns=description https://your-domain.atlassian.net/rest/api/3/settings/columns`  If no column details are sent, then all default columns are removed.  A navigable field is one that can be used as a column on the issue navigator. Find details of navigable issue columns using [Get fields](#api-rest-api-3-field-get).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNavigatorSettingsApi(jira_client.ApiClient(configuration))
body = jira_client.ColumnRequestBody() # ColumnRequestBody | A navigable field value.

try:
    # Set issue navigator default columns
    api_instance.set_issue_navigator_default_columns(body)
except ApiException as e:
    print("Exception when calling IssueNavigatorSettingsApi->set_issue_navigator_default_columns: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ColumnRequestBody**](ColumnRequestBody.md)| A navigable field value. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: */*, multipart/form-data
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

