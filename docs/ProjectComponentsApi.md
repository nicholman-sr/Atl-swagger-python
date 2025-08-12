# jira_client.ProjectComponentsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_component**](ProjectComponentsApi.md#create_component) | **POST** /rest/api/3/component | Create component
[**delete_component**](ProjectComponentsApi.md#delete_component) | **DELETE** /rest/api/3/component/{id} | Delete component
[**find_components_for_projects**](ProjectComponentsApi.md#find_components_for_projects) | **GET** /rest/api/3/component | Find components for projects
[**get_component**](ProjectComponentsApi.md#get_component) | **GET** /rest/api/3/component/{id} | Get component
[**get_component_related_issues**](ProjectComponentsApi.md#get_component_related_issues) | **GET** /rest/api/3/component/{id}/relatedIssueCounts | Get component issues count
[**get_project_components**](ProjectComponentsApi.md#get_project_components) | **GET** /rest/api/3/project/{projectIdOrKey}/components | Get project components
[**get_project_components_paginated**](ProjectComponentsApi.md#get_project_components_paginated) | **GET** /rest/api/3/project/{projectIdOrKey}/component | Get project components paginated
[**update_component**](ProjectComponentsApi.md#update_component) | **PUT** /rest/api/3/component/{id} | Update component

# **create_component**
> ProjectComponent create_component(body)

Create component

Creates a component. Use components to provide containers for issues within a project. Use components to provide containers for issues within a project.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project in which the component is created or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectComponent() # ProjectComponent | 

try:
    # Create component
    api_response = api_instance.create_component(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->create_component: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectComponent**](ProjectComponent.md)|  | 

### Return type

[**ProjectComponent**](ProjectComponent.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_component**
> delete_component(id, move_issues_to=move_issues_to)

Delete component

Deletes a component.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the component or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the component.
move_issues_to = 'move_issues_to_example' # str | The ID of the component to replace the deleted component. If this value is null no replacement is made. (optional)

try:
    # Delete component
    api_instance.delete_component(id, move_issues_to=move_issues_to)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->delete_component: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the component. | 
 **move_issues_to** | **str**| The ID of the component to replace the deleted component. If this value is null no replacement is made. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **find_components_for_projects**
> PageBean2ComponentJsonBean find_components_for_projects(project_ids_or_keys=project_ids_or_keys, start_at=start_at, max_results=max_results, order_by=order_by, query=query)

Find components for projects

Returns a [paginated](#pagination) list of all components in a project, including global (Compass) components when applicable.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
project_ids_or_keys = ['project_ids_or_keys_example'] # list[str] | The project IDs and/or project keys (case sensitive). (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `description` Sorts by the component description.  *  `name` Sorts by component name. (optional)
query = 'query_example' # str | Filter the results using a literal string. Components with a matching `name` or `description` are returned (case insensitive). (optional)

try:
    # Find components for projects
    api_response = api_instance.find_components_for_projects(project_ids_or_keys=project_ids_or_keys, start_at=start_at, max_results=max_results, order_by=order_by, query=query)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->find_components_for_projects: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_ids_or_keys** | [**list[str]**](str.md)| The project IDs and/or project keys (case sensitive). | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;description&#x60; Sorts by the component description.  *  &#x60;name&#x60; Sorts by component name. | [optional] 
 **query** | **str**| Filter the results using a literal string. Components with a matching &#x60;name&#x60; or &#x60;description&#x60; are returned (case insensitive). | [optional] 

### Return type

[**PageBean2ComponentJsonBean**](PageBean2ComponentJsonBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_component**
> ProjectComponent get_component(id)

Get component

Returns a component.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for project containing the component.

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the component.

try:
    # Get component
    api_response = api_instance.get_component(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->get_component: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the component. | 

### Return type

[**ProjectComponent**](ProjectComponent.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_component_related_issues**
> ComponentIssuesCount get_component_related_issues(id)

Get component issues count

Returns the counts of issues assigned to the component.  This operation can be accessed anonymously.  **Deprecation notice:** The required OAuth 2.0 scopes will be updated on June 15, 2024.   *  **Classic**: `read:jira-work`  *  **Granular**: `read:field:jira`, `read:project.component:jira`  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the component.

try:
    # Get component issues count
    api_response = api_instance.get_component_related_issues(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->get_component_related_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the component. | 

### Return type

[**ComponentIssuesCount**](ComponentIssuesCount.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_components**
> list[ProjectComponent] get_project_components(project_id_or_key, component_source=component_source)

Get project components

Returns all components in a project. See the [Get project components paginated](#api-rest-api-3-project-projectIdOrKey-component-get) resource if you want to get a full list of components with pagination.  If your project uses Compass components, this API will return a paginated list of Compass components that are linked to issues in that project.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case sensitive).
component_source = 'jira' # str | The source of the components to return. Can be `jira` (default), `compass` or `auto`. When `auto` is specified, the API will return connected Compass components if the project is opted into Compass, otherwise it will return Jira components. Defaults to `jira`. (optional) (default to jira)

try:
    # Get project components
    api_response = api_instance.get_project_components(project_id_or_key, component_source=component_source)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->get_project_components: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or project key (case sensitive). | 
 **component_source** | **str**| The source of the components to return. Can be &#x60;jira&#x60; (default), &#x60;compass&#x60; or &#x60;auto&#x60;. When &#x60;auto&#x60; is specified, the API will return connected Compass components if the project is opted into Compass, otherwise it will return Jira components. Defaults to &#x60;jira&#x60;. | [optional] [default to jira]

### Return type

[**list[ProjectComponent]**](ProjectComponent.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_components_paginated**
> PageBeanComponentWithIssueCount get_project_components_paginated(project_id_or_key, start_at=start_at, max_results=max_results, order_by=order_by, component_source=component_source, query=query)

Get project components paginated

Returns a [paginated](#pagination) list of all components in a project. See the [Get project components](#api-rest-api-3-project-projectIdOrKey-components-get) resource if you want to get a full list of versions without pagination.  If your project uses Compass components, this API will return a list of Compass components that are linked to issues in that project.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project.

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The project ID or project key (case sensitive).
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `description` Sorts by the component description.  *  `issueCount` Sorts by the count of issues associated with the component.  *  `lead` Sorts by the user key of the component's project lead.  *  `name` Sorts by component name. (optional)
component_source = 'jira' # str | The source of the components to return. Can be `jira` (default), `compass` or `auto`. When `auto` is specified, the API will return connected Compass components if the project is opted into Compass, otherwise it will return Jira components. Defaults to `jira`. (optional) (default to jira)
query = 'query_example' # str | Filter the results using a literal string. Components with a matching `name` or `description` are returned (case insensitive). (optional)

try:
    # Get project components paginated
    api_response = api_instance.get_project_components_paginated(project_id_or_key, start_at=start_at, max_results=max_results, order_by=order_by, component_source=component_source, query=query)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->get_project_components_paginated: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The project ID or project key (case sensitive). | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;description&#x60; Sorts by the component description.  *  &#x60;issueCount&#x60; Sorts by the count of issues associated with the component.  *  &#x60;lead&#x60; Sorts by the user key of the component&#x27;s project lead.  *  &#x60;name&#x60; Sorts by component name. | [optional] 
 **component_source** | **str**| The source of the components to return. Can be &#x60;jira&#x60; (default), &#x60;compass&#x60; or &#x60;auto&#x60;. When &#x60;auto&#x60; is specified, the API will return connected Compass components if the project is opted into Compass, otherwise it will return Jira components. Defaults to &#x60;jira&#x60;. | [optional] [default to jira]
 **query** | **str**| Filter the results using a literal string. Components with a matching &#x60;name&#x60; or &#x60;description&#x60; are returned (case insensitive). | [optional] 

### Return type

[**PageBeanComponentWithIssueCount**](PageBeanComponentWithIssueCount.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_component**
> ProjectComponent update_component(body, id)

Update component

Updates a component. Any fields included in the request are overwritten. If `leadAccountId` is an empty string (\"\") the component lead is removed.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the component or *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ProjectComponentsApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectComponent() # ProjectComponent | 
id = 'id_example' # str | The ID of the component.

try:
    # Update component
    api_response = api_instance.update_component(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectComponentsApi->update_component: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectComponent**](ProjectComponent.md)|  | 
 **id** | **str**| The ID of the component. | 

### Return type

[**ProjectComponent**](ProjectComponent.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

