# jira_client.StatusApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_statuses**](StatusApi.md#create_statuses) | **POST** /rest/api/3/statuses | Bulk create statuses
[**delete_statuses_by_id**](StatusApi.md#delete_statuses_by_id) | **DELETE** /rest/api/3/statuses | Bulk delete Statuses
[**get_project_issue_type_usages_for_status**](StatusApi.md#get_project_issue_type_usages_for_status) | **GET** /rest/api/3/statuses/{statusId}/project/{projectId}/issueTypeUsages | Get issue type usages by status and project
[**get_project_usages_for_status**](StatusApi.md#get_project_usages_for_status) | **GET** /rest/api/3/statuses/{statusId}/projectUsages | Get project usages by status
[**get_statuses_by_id**](StatusApi.md#get_statuses_by_id) | **GET** /rest/api/3/statuses | Bulk get statuses
[**get_workflow_usages_for_status**](StatusApi.md#get_workflow_usages_for_status) | **GET** /rest/api/3/statuses/{statusId}/workflowUsages | Get workflow usages by status
[**search**](StatusApi.md#search) | **GET** /rest/api/3/statuses/search | Search statuses paginated
[**update_statuses**](StatusApi.md#update_statuses) | **PUT** /rest/api/3/statuses | Bulk update statuses

# **create_statuses**
> list[JiraStatus] create_statuses(body)

Bulk create statuses

Creates statuses for a global or project scope.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)  *  *Administer Jira* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
body = jira_client.StatusCreateRequest() # StatusCreateRequest | Details of the statuses being created and their scope.

try:
    # Bulk create statuses
    api_response = api_instance.create_statuses(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->create_statuses: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**StatusCreateRequest**](StatusCreateRequest.md)| Details of the statuses being created and their scope. | 

### Return type

[**list[JiraStatus]**](JiraStatus.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_statuses_by_id**
> object delete_statuses_by_id(id)

Bulk delete Statuses

Deletes statuses by ID.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)  *  *Administer Jira* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
id = ['id_example'] # list[str] | The list of status IDs. To include multiple IDs, provide an ampersand-separated list. For example, id=10000&id=10001.  Min items `1`, Max items `50`

try:
    # Bulk delete Statuses
    api_response = api_instance.delete_statuses_by_id(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->delete_statuses_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | [**list[str]**](str.md)| The list of status IDs. To include multiple IDs, provide an ampersand-separated list. For example, id&#x3D;10000&amp;id&#x3D;10001.  Min items &#x60;1&#x60;, Max items &#x60;50&#x60; | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_issue_type_usages_for_status**
> StatusProjectIssueTypeUsageDTO get_project_issue_type_usages_for_status(status_id, project_id, next_page_token=next_page_token, max_results=max_results)

Get issue type usages by status and project

Returns a page of issue types in a project using a given status.

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
status_id = 'status_id_example' # str | The statusId to fetch issue type usages for
project_id = 'project_id_example' # str | The projectId to fetch issue type usages for
next_page_token = 'next_page_token_example' # str | The cursor for pagination (optional)
max_results = 50 # int | The maximum number of results to return. Must be an integer between 1 and 200. (optional) (default to 50)

try:
    # Get issue type usages by status and project
    api_response = api_instance.get_project_issue_type_usages_for_status(status_id, project_id, next_page_token=next_page_token, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->get_project_issue_type_usages_for_status: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status_id** | **str**| The statusId to fetch issue type usages for | 
 **project_id** | **str**| The projectId to fetch issue type usages for | 
 **next_page_token** | **str**| The cursor for pagination | [optional] 
 **max_results** | **int**| The maximum number of results to return. Must be an integer between 1 and 200. | [optional] [default to 50]

### Return type

[**StatusProjectIssueTypeUsageDTO**](StatusProjectIssueTypeUsageDTO.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_usages_for_status**
> StatusProjectUsageDTO get_project_usages_for_status(status_id, next_page_token=next_page_token, max_results=max_results)

Get project usages by status

Returns a page of projects using a given status.

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
status_id = 'status_id_example' # str | The statusId to fetch project usages for
next_page_token = 'next_page_token_example' # str | The cursor for pagination (optional)
max_results = 50 # int | The maximum number of results to return. Must be an integer between 1 and 200. (optional) (default to 50)

try:
    # Get project usages by status
    api_response = api_instance.get_project_usages_for_status(status_id, next_page_token=next_page_token, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->get_project_usages_for_status: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status_id** | **str**| The statusId to fetch project usages for | 
 **next_page_token** | **str**| The cursor for pagination | [optional] 
 **max_results** | **int**| The maximum number of results to return. Must be an integer between 1 and 200. | [optional] [default to 50]

### Return type

[**StatusProjectUsageDTO**](StatusProjectUsageDTO.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_statuses_by_id**
> list[JiraStatus] get_statuses_by_id(id)

Bulk get statuses

Returns a list of the statuses specified by one or more status IDs.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)  *  *Administer Jira* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
id = ['id_example'] # list[str] | The list of status IDs. To include multiple IDs, provide an ampersand-separated list. For example, id=10000&id=10001.  Min items `1`, Max items `50`

try:
    # Bulk get statuses
    api_response = api_instance.get_statuses_by_id(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->get_statuses_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | [**list[str]**](str.md)| The list of status IDs. To include multiple IDs, provide an ampersand-separated list. For example, id&#x3D;10000&amp;id&#x3D;10001.  Min items &#x60;1&#x60;, Max items &#x60;50&#x60; | 

### Return type

[**list[JiraStatus]**](JiraStatus.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_usages_for_status**
> StatusWorkflowUsageDTO get_workflow_usages_for_status(status_id, next_page_token=next_page_token, max_results=max_results)

Get workflow usages by status

Returns a page of workflows using a given status.

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
status_id = 'status_id_example' # str | The statusId to fetch workflow usages for
next_page_token = 'next_page_token_example' # str | The cursor for pagination (optional)
max_results = 50 # int | The maximum number of results to return. Must be an integer between 1 and 200. (optional) (default to 50)

try:
    # Get workflow usages by status
    api_response = api_instance.get_workflow_usages_for_status(status_id, next_page_token=next_page_token, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->get_workflow_usages_for_status: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **status_id** | **str**| The statusId to fetch workflow usages for | 
 **next_page_token** | **str**| The cursor for pagination | [optional] 
 **max_results** | **int**| The maximum number of results to return. Must be an integer between 1 and 200. | [optional] [default to 50]

### Return type

[**StatusWorkflowUsageDTO**](StatusWorkflowUsageDTO.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search**
> PageOfStatuses search(project_id=project_id, start_at=start_at, max_results=max_results, search_string=search_string, status_category=status_category)

Search statuses paginated

Returns a [paginated](https://developer.atlassian.com/cloud/jira/platform/rest/v3/intro/#pagination) list of statuses that match a search on name or project.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)  *  *Administer Jira* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
project_id = 'project_id_example' # str | The project the status is part of or null for global statuses. (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 200 # int | The maximum number of items to return per page. (optional) (default to 200)
search_string = 'search_string_example' # str | Term to match status names against or null to search for all statuses in the search scope. (optional)
status_category = 'status_category_example' # str | Category of the status to filter by. The supported values are: `TODO`, `IN_PROGRESS`, and `DONE`. (optional)

try:
    # Search statuses paginated
    api_response = api_instance.search(project_id=project_id, start_at=start_at, max_results=max_results, search_string=search_string, status_category=status_category)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->search: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | **str**| The project the status is part of or null for global statuses. | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 200]
 **search_string** | **str**| Term to match status names against or null to search for all statuses in the search scope. | [optional] 
 **status_category** | **str**| Category of the status to filter by. The supported values are: &#x60;TODO&#x60;, &#x60;IN_PROGRESS&#x60;, and &#x60;DONE&#x60;. | [optional] 

### Return type

[**PageOfStatuses**](PageOfStatuses.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_statuses**
> object update_statuses(body)

Bulk update statuses

Updates statuses by ID.  **[Permissions](#permissions) required:**   *  *Administer projects* [project permission.](https://confluence.atlassian.com/x/yodKLg)  *  *Administer Jira* [project permission.](https://confluence.atlassian.com/x/yodKLg)

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
api_instance = jira_client.StatusApi(jira_client.ApiClient(configuration))
body = jira_client.StatusUpdateRequest() # StatusUpdateRequest | The list of statuses that will be updated.

try:
    # Bulk update statuses
    api_response = api_instance.update_statuses(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling StatusApi->update_statuses: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**StatusUpdateRequest**](StatusUpdateRequest.md)| The list of statuses that will be updated. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

