# jira_client.PrioritySchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_priority_scheme**](PrioritySchemesApi.md#create_priority_scheme) | **POST** /rest/api/3/priorityscheme | Create priority scheme
[**delete_priority_scheme**](PrioritySchemesApi.md#delete_priority_scheme) | **DELETE** /rest/api/3/priorityscheme/{schemeId} | Delete priority scheme
[**get_available_priorities_by_priority_scheme**](PrioritySchemesApi.md#get_available_priorities_by_priority_scheme) | **GET** /rest/api/3/priorityscheme/priorities/available | Get available priorities by priority scheme
[**get_priorities_by_priority_scheme**](PrioritySchemesApi.md#get_priorities_by_priority_scheme) | **GET** /rest/api/3/priorityscheme/{schemeId}/priorities | Get priorities by priority scheme
[**get_priority_schemes**](PrioritySchemesApi.md#get_priority_schemes) | **GET** /rest/api/3/priorityscheme | Get priority schemes
[**get_projects_by_priority_scheme**](PrioritySchemesApi.md#get_projects_by_priority_scheme) | **GET** /rest/api/3/priorityscheme/{schemeId}/projects | Get projects by priority scheme
[**suggested_priorities_for_mappings**](PrioritySchemesApi.md#suggested_priorities_for_mappings) | **POST** /rest/api/3/priorityscheme/mappings | Suggested priorities for mappings
[**update_priority_scheme**](PrioritySchemesApi.md#update_priority_scheme) | **PUT** /rest/api/3/priorityscheme/{schemeId} | Update priority scheme

# **create_priority_scheme**
> PrioritySchemeId create_priority_scheme(body)

Create priority scheme

Creates a new priority scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.CreatePrioritySchemeDetails() # CreatePrioritySchemeDetails | 

try:
    # Create priority scheme
    api_response = api_instance.create_priority_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->create_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CreatePrioritySchemeDetails**](CreatePrioritySchemeDetails.md)|  | 

### Return type

[**PrioritySchemeId**](PrioritySchemeId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_priority_scheme**
> object delete_priority_scheme(scheme_id)

Delete priority scheme

Deletes a priority scheme.  This operation is only available for priority schemes without any associated projects. Any associated projects must be removed from the priority scheme before this operation can be performed.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 789 # int | The priority scheme ID.

try:
    # Delete priority scheme
    api_response = api_instance.delete_priority_scheme(scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->delete_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **int**| The priority scheme ID. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_available_priorities_by_priority_scheme**
> PageBeanPriorityWithSequence get_available_priorities_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results, query=query, exclude=exclude)

Get available priorities by priority scheme

Returns a [paginated](#pagination) list of priorities available for adding to a priority scheme.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The priority scheme ID.
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
query = '' # str | The string to query priorities on by name. (optional)
exclude = ['exclude_example'] # list[str] | A list of priority IDs to exclude from the results. (optional)

try:
    # Get available priorities by priority scheme
    api_response = api_instance.get_available_priorities_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results, query=query, exclude=exclude)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->get_available_priorities_by_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The priority scheme ID. | 
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **query** | **str**| The string to query priorities on by name. | [optional] 
 **exclude** | [**list[str]**](str.md)| A list of priority IDs to exclude from the results. | [optional] 

### Return type

[**PageBeanPriorityWithSequence**](PageBeanPriorityWithSequence.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_priorities_by_priority_scheme**
> PageBeanPriorityWithSequence get_priorities_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results)

Get priorities by priority scheme

Returns a [paginated](#pagination) list of priorities by scheme.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The priority scheme ID.
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get priorities by priority scheme
    api_response = api_instance.get_priorities_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->get_priorities_by_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The priority scheme ID. | 
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageBeanPriorityWithSequence**](PageBeanPriorityWithSequence.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_priority_schemes**
> PageBeanPrioritySchemeWithPaginatedPrioritiesAndProjects get_priority_schemes(start_at=start_at, max_results=max_results, priority_id=priority_id, scheme_id=scheme_id, scheme_name=scheme_name, only_default=only_default, order_by=order_by, expand=expand)

Get priority schemes

Returns a [paginated](#pagination) list of priority schemes.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
priority_id = [56] # list[int] | A set of priority IDs to filter by. To include multiple IDs, provide an ampersand-separated list. For example, `priorityId=10000&priorityId=10001`. (optional)
scheme_id = [56] # list[int] | A set of priority scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, `schemeId=10000&schemeId=10001`. (optional)
scheme_name = '' # str | The name of scheme to search for. (optional)
only_default = false # bool | Whether only the default priority is returned. (optional) (default to false)
order_by = '+name' # str | The ordering to return the priority schemes by. (optional) (default to +name)
expand = 'expand_example' # str | A comma separated list of additional information to return. \"priorities\" will return priorities associated with the priority scheme. \"projects\" will return projects associated with the priority scheme. `expand=priorities,projects`. (optional)

try:
    # Get priority schemes
    api_response = api_instance.get_priority_schemes(start_at=start_at, max_results=max_results, priority_id=priority_id, scheme_id=scheme_id, scheme_name=scheme_name, only_default=only_default, order_by=order_by, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->get_priority_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **priority_id** | [**list[int]**](int.md)| A set of priority IDs to filter by. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;priorityId&#x3D;10000&amp;priorityId&#x3D;10001&#x60;. | [optional] 
 **scheme_id** | [**list[int]**](int.md)| A set of priority scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;schemeId&#x3D;10000&amp;schemeId&#x3D;10001&#x60;. | [optional] 
 **scheme_name** | **str**| The name of scheme to search for. | [optional] 
 **only_default** | **bool**| Whether only the default priority is returned. | [optional] [default to false]
 **order_by** | **str**| The ordering to return the priority schemes by. | [optional] [default to +name]
 **expand** | **str**| A comma separated list of additional information to return. \&quot;priorities\&quot; will return priorities associated with the priority scheme. \&quot;projects\&quot; will return projects associated with the priority scheme. &#x60;expand&#x3D;priorities,projects&#x60;. | [optional] 

### Return type

[**PageBeanPrioritySchemeWithPaginatedPrioritiesAndProjects**](PageBeanPrioritySchemeWithPaginatedPrioritiesAndProjects.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_projects_by_priority_scheme**
> PageBeanProject get_projects_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results, project_id=project_id, query=query)

Get projects by priority scheme

Returns a [paginated](#pagination) list of projects by scheme.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The priority scheme ID.
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
project_id = [56] # list[int] | The project IDs to filter by. For example, `projectId=10000&projectId=10001`. (optional)
query = '' # str | The string to query projects on by name. (optional)

try:
    # Get projects by priority scheme
    api_response = api_instance.get_projects_by_priority_scheme(scheme_id, start_at=start_at, max_results=max_results, project_id=project_id, query=query)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->get_projects_by_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The priority scheme ID. | 
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **project_id** | [**list[int]**](int.md)| The project IDs to filter by. For example, &#x60;projectId&#x3D;10000&amp;projectId&#x3D;10001&#x60;. | [optional] 
 **query** | **str**| The string to query projects on by name. | [optional] 

### Return type

[**PageBeanProject**](PageBeanProject.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **suggested_priorities_for_mappings**
> PageBeanPriorityWithSequence suggested_priorities_for_mappings(body)

Suggested priorities for mappings

Returns a [paginated](#pagination) list of priorities that would require mapping, given a change in priorities or projects associated with a priority scheme.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.SuggestedMappingsRequestBean() # SuggestedMappingsRequestBean | 

try:
    # Suggested priorities for mappings
    api_response = api_instance.suggested_priorities_for_mappings(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->suggested_priorities_for_mappings: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SuggestedMappingsRequestBean**](SuggestedMappingsRequestBean.md)|  | 

### Return type

[**PageBeanPriorityWithSequence**](PageBeanPriorityWithSequence.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_priority_scheme**
> UpdatePrioritySchemeResponseBean update_priority_scheme(body, scheme_id)

Update priority scheme

Updates a priority scheme. This includes its details, the lists of priorities and projects in it  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PrioritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.UpdatePrioritySchemeRequestBean() # UpdatePrioritySchemeRequestBean | 
scheme_id = 789 # int | The ID of the priority scheme.

try:
    # Update priority scheme
    api_response = api_instance.update_priority_scheme(body, scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PrioritySchemesApi->update_priority_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdatePrioritySchemeRequestBean**](UpdatePrioritySchemeRequestBean.md)|  | 
 **scheme_id** | **int**| The ID of the priority scheme. | 

### Return type

[**UpdatePrioritySchemeResponseBean**](UpdatePrioritySchemeResponseBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

