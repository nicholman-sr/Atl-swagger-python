# jira_client.IssueTypeSchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_issue_types_to_issue_type_scheme**](IssueTypeSchemesApi.md#add_issue_types_to_issue_type_scheme) | **PUT** /rest/api/3/issuetypescheme/{issueTypeSchemeId}/issuetype | Add issue types to issue type scheme
[**assign_issue_type_scheme_to_project**](IssueTypeSchemesApi.md#assign_issue_type_scheme_to_project) | **PUT** /rest/api/3/issuetypescheme/project | Assign issue type scheme to project
[**create_issue_type_scheme**](IssueTypeSchemesApi.md#create_issue_type_scheme) | **POST** /rest/api/3/issuetypescheme | Create issue type scheme
[**delete_issue_type_scheme**](IssueTypeSchemesApi.md#delete_issue_type_scheme) | **DELETE** /rest/api/3/issuetypescheme/{issueTypeSchemeId} | Delete issue type scheme
[**get_all_issue_type_schemes**](IssueTypeSchemesApi.md#get_all_issue_type_schemes) | **GET** /rest/api/3/issuetypescheme | Get all issue type schemes
[**get_issue_type_scheme_for_projects**](IssueTypeSchemesApi.md#get_issue_type_scheme_for_projects) | **GET** /rest/api/3/issuetypescheme/project | Get issue type schemes for projects
[**get_issue_type_schemes_mapping**](IssueTypeSchemesApi.md#get_issue_type_schemes_mapping) | **GET** /rest/api/3/issuetypescheme/mapping | Get issue type scheme items
[**remove_issue_type_from_issue_type_scheme**](IssueTypeSchemesApi.md#remove_issue_type_from_issue_type_scheme) | **DELETE** /rest/api/3/issuetypescheme/{issueTypeSchemeId}/issuetype/{issueTypeId} | Remove issue type from issue type scheme
[**reorder_issue_types_in_issue_type_scheme**](IssueTypeSchemesApi.md#reorder_issue_types_in_issue_type_scheme) | **PUT** /rest/api/3/issuetypescheme/{issueTypeSchemeId}/issuetype/move | Change order of issue types
[**update_issue_type_scheme**](IssueTypeSchemesApi.md#update_issue_type_scheme) | **PUT** /rest/api/3/issuetypescheme/{issueTypeSchemeId} | Update issue type scheme

# **add_issue_types_to_issue_type_scheme**
> object add_issue_types_to_issue_type_scheme(body, issue_type_scheme_id)

Add issue types to issue type scheme

Adds issue types to an issue type scheme.  The added issue types are appended to the issue types list.  If any of the issue types exist in the issue type scheme, the operation fails and no issue types are added.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeIds() # IssueTypeIds | 
issue_type_scheme_id = 789 # int | The ID of the issue type scheme.

try:
    # Add issue types to issue type scheme
    api_response = api_instance.add_issue_types_to_issue_type_scheme(body, issue_type_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->add_issue_types_to_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeIds**](IssueTypeIds.md)|  | 
 **issue_type_scheme_id** | **int**| The ID of the issue type scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **assign_issue_type_scheme_to_project**
> object assign_issue_type_scheme_to_project(body)

Assign issue type scheme to project

Assigns an issue type scheme to a project.  If any issues in the project are assigned issue types not present in the new scheme, the operation will fail. To complete the assignment those issues must be updated to use issue types in the new scheme.  Issue type schemes can only be assigned to classic projects.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeSchemeProjectAssociation() # IssueTypeSchemeProjectAssociation | 

try:
    # Assign issue type scheme to project
    api_response = api_instance.assign_issue_type_scheme_to_project(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->assign_issue_type_scheme_to_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeSchemeProjectAssociation**](IssueTypeSchemeProjectAssociation.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issue_type_scheme**
> IssueTypeSchemeID create_issue_type_scheme(body)

Create issue type scheme

Creates an issue type scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeSchemeDetails() # IssueTypeSchemeDetails | 

try:
    # Create issue type scheme
    api_response = api_instance.create_issue_type_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->create_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeSchemeDetails**](IssueTypeSchemeDetails.md)|  | 

### Return type

[**IssueTypeSchemeID**](IssueTypeSchemeID.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_issue_type_scheme**
> object delete_issue_type_scheme(issue_type_scheme_id)

Delete issue type scheme

Deletes an issue type scheme.  Only issue type schemes used in classic projects can be deleted.  Any projects assigned to the scheme are reassigned to the default issue type scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
issue_type_scheme_id = 789 # int | The ID of the issue type scheme.

try:
    # Delete issue type scheme
    api_response = api_instance.delete_issue_type_scheme(issue_type_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->delete_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_type_scheme_id** | **int**| The ID of the issue type scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_issue_type_schemes**
> PageBeanIssueTypeScheme get_all_issue_type_schemes(start_at=start_at, max_results=max_results, id=id, order_by=order_by, expand=expand, query_string=query_string)

Get all issue type schemes

Returns a [paginated](#pagination) list of issue type schemes.  Only issue type schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
id = [56] # list[int] | The list of issue type schemes IDs. To include multiple IDs, provide an ampersand-separated list. For example, `id=10000&id=10001`. (optional)
order_by = 'id' # str | [Order](#ordering) the results by a field:   *  `name` Sorts by issue type scheme name.  *  `id` Sorts by issue type scheme ID. (optional) (default to id)
expand = '' # str | Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  `projects` For each issue type schemes, returns information about the projects the issue type scheme is assigned to.  *  `issueTypes` For each issue type schemes, returns information about the issueTypes the issue type scheme have. (optional)
query_string = '' # str | String used to perform a case-insensitive partial match with issue type scheme name. (optional)

try:
    # Get all issue type schemes
    api_response = api_instance.get_all_issue_type_schemes(start_at=start_at, max_results=max_results, id=id, order_by=order_by, expand=expand, query_string=query_string)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->get_all_issue_type_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[int]**](int.md)| The list of issue type schemes IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;name&#x60; Sorts by issue type scheme name.  *  &#x60;id&#x60; Sorts by issue type scheme ID. | [optional] [default to id]
 **expand** | **str**| Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;projects&#x60; For each issue type schemes, returns information about the projects the issue type scheme is assigned to.  *  &#x60;issueTypes&#x60; For each issue type schemes, returns information about the issueTypes the issue type scheme have. | [optional] 
 **query_string** | **str**| String used to perform a case-insensitive partial match with issue type scheme name. | [optional] 

### Return type

[**PageBeanIssueTypeScheme**](PageBeanIssueTypeScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type_scheme_for_projects**
> PageBeanIssueTypeSchemeProjects get_issue_type_scheme_for_projects(project_id, start_at=start_at, max_results=max_results)

Get issue type schemes for projects

Returns a [paginated](#pagination) list of issue type schemes and, for each issue type scheme, a list of the projects that use it.  Only issue type schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
project_id = [56] # list[int] | The list of project IDs. To include multiple project IDs, provide an ampersand-separated list. For example, `projectId=10000&projectId=10001`.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get issue type schemes for projects
    api_response = api_instance.get_issue_type_scheme_for_projects(project_id, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->get_issue_type_scheme_for_projects: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | [**list[int]**](int.md)| The list of project IDs. To include multiple project IDs, provide an ampersand-separated list. For example, &#x60;projectId&#x3D;10000&amp;projectId&#x3D;10001&#x60;. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageBeanIssueTypeSchemeProjects**](PageBeanIssueTypeSchemeProjects.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type_schemes_mapping**
> PageBeanIssueTypeSchemeMapping get_issue_type_schemes_mapping(start_at=start_at, max_results=max_results, issue_type_scheme_id=issue_type_scheme_id)

Get issue type scheme items

Returns a [paginated](#pagination) list of issue type scheme items.  Only issue type scheme items used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
issue_type_scheme_id = [56] # list[int] | The list of issue type scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, `issueTypeSchemeId=10000&issueTypeSchemeId=10001`. (optional)

try:
    # Get issue type scheme items
    api_response = api_instance.get_issue_type_schemes_mapping(start_at=start_at, max_results=max_results, issue_type_scheme_id=issue_type_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->get_issue_type_schemes_mapping: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **issue_type_scheme_id** | [**list[int]**](int.md)| The list of issue type scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;issueTypeSchemeId&#x3D;10000&amp;issueTypeSchemeId&#x3D;10001&#x60;. | [optional] 

### Return type

[**PageBeanIssueTypeSchemeMapping**](PageBeanIssueTypeSchemeMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_issue_type_from_issue_type_scheme**
> object remove_issue_type_from_issue_type_scheme(issue_type_scheme_id, issue_type_id)

Remove issue type from issue type scheme

Removes an issue type from an issue type scheme.  This operation cannot remove:   *  any issue type used by issues.  *  any issue types from the default issue type scheme.  *  the last standard issue type from an issue type scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
issue_type_scheme_id = 789 # int | The ID of the issue type scheme.
issue_type_id = 789 # int | The ID of the issue type.

try:
    # Remove issue type from issue type scheme
    api_response = api_instance.remove_issue_type_from_issue_type_scheme(issue_type_scheme_id, issue_type_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->remove_issue_type_from_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_type_scheme_id** | **int**| The ID of the issue type scheme. | 
 **issue_type_id** | **int**| The ID of the issue type. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reorder_issue_types_in_issue_type_scheme**
> object reorder_issue_types_in_issue_type_scheme(body, issue_type_scheme_id)

Change order of issue types

Changes the order of issue types in an issue type scheme.  The request body parameters must meet the following requirements:   *  all of the issue types must belong to the issue type scheme.  *  either `after` or `position` must be provided.  *  the issue type in `after` must not be in the issue type list.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.OrderOfIssueTypes() # OrderOfIssueTypes | 
issue_type_scheme_id = 789 # int | The ID of the issue type scheme.

try:
    # Change order of issue types
    api_response = api_instance.reorder_issue_types_in_issue_type_scheme(body, issue_type_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->reorder_issue_types_in_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**OrderOfIssueTypes**](OrderOfIssueTypes.md)|  | 
 **issue_type_scheme_id** | **int**| The ID of the issue type scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_issue_type_scheme**
> object update_issue_type_scheme(body, issue_type_scheme_id)

Update issue type scheme

Updates an issue type scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeSchemeUpdateDetails() # IssueTypeSchemeUpdateDetails | 
issue_type_scheme_id = 789 # int | The ID of the issue type scheme.

try:
    # Update issue type scheme
    api_response = api_instance.update_issue_type_scheme(body, issue_type_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeSchemesApi->update_issue_type_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeSchemeUpdateDetails**](IssueTypeSchemeUpdateDetails.md)|  | 
 **issue_type_scheme_id** | **int**| The ID of the issue type scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

