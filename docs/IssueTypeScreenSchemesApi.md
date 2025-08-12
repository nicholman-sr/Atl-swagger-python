# jira_client.IssueTypeScreenSchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**append_mappings_for_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#append_mappings_for_issue_type_screen_scheme) | **PUT** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId}/mapping | Append mappings to issue type screen scheme
[**assign_issue_type_screen_scheme_to_project**](IssueTypeScreenSchemesApi.md#assign_issue_type_screen_scheme_to_project) | **PUT** /rest/api/3/issuetypescreenscheme/project | Assign issue type screen scheme to project
[**create_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#create_issue_type_screen_scheme) | **POST** /rest/api/3/issuetypescreenscheme | Create issue type screen scheme
[**delete_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#delete_issue_type_screen_scheme) | **DELETE** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId} | Delete issue type screen scheme
[**get_issue_type_screen_scheme_mappings**](IssueTypeScreenSchemesApi.md#get_issue_type_screen_scheme_mappings) | **GET** /rest/api/3/issuetypescreenscheme/mapping | Get issue type screen scheme items
[**get_issue_type_screen_scheme_project_associations**](IssueTypeScreenSchemesApi.md#get_issue_type_screen_scheme_project_associations) | **GET** /rest/api/3/issuetypescreenscheme/project | Get issue type screen schemes for projects
[**get_issue_type_screen_schemes**](IssueTypeScreenSchemesApi.md#get_issue_type_screen_schemes) | **GET** /rest/api/3/issuetypescreenscheme | Get issue type screen schemes
[**get_projects_for_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#get_projects_for_issue_type_screen_scheme) | **GET** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId}/project | Get issue type screen scheme projects
[**remove_mappings_from_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#remove_mappings_from_issue_type_screen_scheme) | **POST** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId}/mapping/remove | Remove mappings from issue type screen scheme
[**update_default_screen_scheme**](IssueTypeScreenSchemesApi.md#update_default_screen_scheme) | **PUT** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId}/mapping/default | Update issue type screen scheme default screen scheme
[**update_issue_type_screen_scheme**](IssueTypeScreenSchemesApi.md#update_issue_type_screen_scheme) | **PUT** /rest/api/3/issuetypescreenscheme/{issueTypeScreenSchemeId} | Update issue type screen scheme

# **append_mappings_for_issue_type_screen_scheme**
> object append_mappings_for_issue_type_screen_scheme(body, issue_type_screen_scheme_id)

Append mappings to issue type screen scheme

Appends issue type to screen scheme mappings to an issue type screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeScreenSchemeMappingDetails() # IssueTypeScreenSchemeMappingDetails | 
issue_type_screen_scheme_id = 'issue_type_screen_scheme_id_example' # str | The ID of the issue type screen scheme.

try:
    # Append mappings to issue type screen scheme
    api_response = api_instance.append_mappings_for_issue_type_screen_scheme(body, issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->append_mappings_for_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeScreenSchemeMappingDetails**](IssueTypeScreenSchemeMappingDetails.md)|  | 
 **issue_type_screen_scheme_id** | **str**| The ID of the issue type screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **assign_issue_type_screen_scheme_to_project**
> object assign_issue_type_screen_scheme_to_project(body)

Assign issue type screen scheme to project

Assigns an issue type screen scheme to a project.  Issue type screen schemes can only be assigned to classic projects.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeScreenSchemeProjectAssociation() # IssueTypeScreenSchemeProjectAssociation | 

try:
    # Assign issue type screen scheme to project
    api_response = api_instance.assign_issue_type_screen_scheme_to_project(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->assign_issue_type_screen_scheme_to_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeScreenSchemeProjectAssociation**](IssueTypeScreenSchemeProjectAssociation.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issue_type_screen_scheme**
> IssueTypeScreenSchemeId create_issue_type_screen_scheme(body)

Create issue type screen scheme

Creates an issue type screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeScreenSchemeDetails() # IssueTypeScreenSchemeDetails | An issue type screen scheme bean.

try:
    # Create issue type screen scheme
    api_response = api_instance.create_issue_type_screen_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->create_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeScreenSchemeDetails**](IssueTypeScreenSchemeDetails.md)| An issue type screen scheme bean. | 

### Return type

[**IssueTypeScreenSchemeId**](IssueTypeScreenSchemeId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_issue_type_screen_scheme**
> object delete_issue_type_screen_scheme(issue_type_screen_scheme_id)

Delete issue type screen scheme

Deletes an issue type screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
issue_type_screen_scheme_id = 'issue_type_screen_scheme_id_example' # str | The ID of the issue type screen scheme.

try:
    # Delete issue type screen scheme
    api_response = api_instance.delete_issue_type_screen_scheme(issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->delete_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_type_screen_scheme_id** | **str**| The ID of the issue type screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type_screen_scheme_mappings**
> PageBeanIssueTypeScreenSchemeItem get_issue_type_screen_scheme_mappings(start_at=start_at, max_results=max_results, issue_type_screen_scheme_id=issue_type_screen_scheme_id)

Get issue type screen scheme items

Returns a [paginated](#pagination) list of issue type screen scheme items.  Only issue type screen schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
issue_type_screen_scheme_id = [56] # list[int] | The list of issue type screen scheme IDs. To include multiple issue type screen schemes, separate IDs with ampersand: `issueTypeScreenSchemeId=10000&issueTypeScreenSchemeId=10001`. (optional)

try:
    # Get issue type screen scheme items
    api_response = api_instance.get_issue_type_screen_scheme_mappings(start_at=start_at, max_results=max_results, issue_type_screen_scheme_id=issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->get_issue_type_screen_scheme_mappings: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **issue_type_screen_scheme_id** | [**list[int]**](int.md)| The list of issue type screen scheme IDs. To include multiple issue type screen schemes, separate IDs with ampersand: &#x60;issueTypeScreenSchemeId&#x3D;10000&amp;issueTypeScreenSchemeId&#x3D;10001&#x60;. | [optional] 

### Return type

[**PageBeanIssueTypeScreenSchemeItem**](PageBeanIssueTypeScreenSchemeItem.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type_screen_scheme_project_associations**
> PageBeanIssueTypeScreenSchemesProjects get_issue_type_screen_scheme_project_associations(project_id, start_at=start_at, max_results=max_results)

Get issue type screen schemes for projects

Returns a [paginated](#pagination) list of issue type screen schemes and, for each issue type screen scheme, a list of the projects that use it.  Only issue type screen schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
project_id = [56] # list[int] | The list of project IDs. To include multiple projects, separate IDs with ampersand: `projectId=10000&projectId=10001`.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get issue type screen schemes for projects
    api_response = api_instance.get_issue_type_screen_scheme_project_associations(project_id, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->get_issue_type_screen_scheme_project_associations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | [**list[int]**](int.md)| The list of project IDs. To include multiple projects, separate IDs with ampersand: &#x60;projectId&#x3D;10000&amp;projectId&#x3D;10001&#x60;. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageBeanIssueTypeScreenSchemesProjects**](PageBeanIssueTypeScreenSchemesProjects.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_type_screen_schemes**
> PageBeanIssueTypeScreenScheme get_issue_type_screen_schemes(start_at=start_at, max_results=max_results, id=id, query_string=query_string, order_by=order_by, expand=expand)

Get issue type screen schemes

Returns a [paginated](#pagination) list of issue type screen schemes.  Only issue type screen schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
id = [56] # list[int] | The list of issue type screen scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, `id=10000&id=10001`. (optional)
query_string = '' # str | String used to perform a case-insensitive partial match with issue type screen scheme name. (optional)
order_by = 'id' # str | [Order](#ordering) the results by a field:   *  `name` Sorts by issue type screen scheme name.  *  `id` Sorts by issue type screen scheme ID. (optional) (default to id)
expand = '' # str | Use [expand](#expansion) to include additional information in the response. This parameter accepts `projects` that, for each issue type screen schemes, returns information about the projects the issue type screen scheme is assigned to. (optional)

try:
    # Get issue type screen schemes
    api_response = api_instance.get_issue_type_screen_schemes(start_at=start_at, max_results=max_results, id=id, query_string=query_string, order_by=order_by, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->get_issue_type_screen_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[int]**](int.md)| The list of issue type screen scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **query_string** | **str**| String used to perform a case-insensitive partial match with issue type screen scheme name. | [optional] 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;name&#x60; Sorts by issue type screen scheme name.  *  &#x60;id&#x60; Sorts by issue type screen scheme ID. | [optional] [default to id]
 **expand** | **str**| Use [expand](#expansion) to include additional information in the response. This parameter accepts &#x60;projects&#x60; that, for each issue type screen schemes, returns information about the projects the issue type screen scheme is assigned to. | [optional] 

### Return type

[**PageBeanIssueTypeScreenScheme**](PageBeanIssueTypeScreenScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_projects_for_issue_type_screen_scheme**
> PageBeanProjectDetails get_projects_for_issue_type_screen_scheme(issue_type_screen_scheme_id, start_at=start_at, max_results=max_results, query=query)

Get issue type screen scheme projects

Returns a [paginated](#pagination) list of projects associated with an issue type screen scheme.  Only company-managed projects associated with an issue type screen scheme are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
issue_type_screen_scheme_id = 789 # int | The ID of the issue type screen scheme.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
query = '' # str |  (optional)

try:
    # Get issue type screen scheme projects
    api_response = api_instance.get_projects_for_issue_type_screen_scheme(issue_type_screen_scheme_id, start_at=start_at, max_results=max_results, query=query)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->get_projects_for_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_type_screen_scheme_id** | **int**| The ID of the issue type screen scheme. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **query** | **str**|  | [optional] 

### Return type

[**PageBeanProjectDetails**](PageBeanProjectDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_mappings_from_issue_type_screen_scheme**
> object remove_mappings_from_issue_type_screen_scheme(body, issue_type_screen_scheme_id)

Remove mappings from issue type screen scheme

Removes issue type to screen scheme mappings from an issue type screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeIds() # IssueTypeIds | 
issue_type_screen_scheme_id = 'issue_type_screen_scheme_id_example' # str | The ID of the issue type screen scheme.

try:
    # Remove mappings from issue type screen scheme
    api_response = api_instance.remove_mappings_from_issue_type_screen_scheme(body, issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->remove_mappings_from_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeIds**](IssueTypeIds.md)|  | 
 **issue_type_screen_scheme_id** | **str**| The ID of the issue type screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_default_screen_scheme**
> object update_default_screen_scheme(body, issue_type_screen_scheme_id)

Update issue type screen scheme default screen scheme

Updates the default screen scheme of an issue type screen scheme. The default screen scheme is used for all unmapped issue types.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateDefaultScreenScheme() # UpdateDefaultScreenScheme | 
issue_type_screen_scheme_id = 'issue_type_screen_scheme_id_example' # str | The ID of the issue type screen scheme.

try:
    # Update issue type screen scheme default screen scheme
    api_response = api_instance.update_default_screen_scheme(body, issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->update_default_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateDefaultScreenScheme**](UpdateDefaultScreenScheme.md)|  | 
 **issue_type_screen_scheme_id** | **str**| The ID of the issue type screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_issue_type_screen_scheme**
> object update_issue_type_screen_scheme(body, issue_type_screen_scheme_id)

Update issue type screen scheme

Updates an issue type screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueTypeScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeScreenSchemeUpdateDetails() # IssueTypeScreenSchemeUpdateDetails | The issue type screen scheme update details.
issue_type_screen_scheme_id = 'issue_type_screen_scheme_id_example' # str | The ID of the issue type screen scheme.

try:
    # Update issue type screen scheme
    api_response = api_instance.update_issue_type_screen_scheme(body, issue_type_screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueTypeScreenSchemesApi->update_issue_type_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeScreenSchemeUpdateDetails**](IssueTypeScreenSchemeUpdateDetails.md)| The issue type screen scheme update details. | 
 **issue_type_screen_scheme_id** | **str**| The ID of the issue type screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

