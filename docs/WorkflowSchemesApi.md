# jira_client.WorkflowSchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_workflow_scheme**](WorkflowSchemesApi.md#create_workflow_scheme) | **POST** /rest/api/3/workflowscheme | Create workflow scheme
[**delete_default_workflow**](WorkflowSchemesApi.md#delete_default_workflow) | **DELETE** /rest/api/3/workflowscheme/{id}/default | Delete default workflow
[**delete_workflow_mapping**](WorkflowSchemesApi.md#delete_workflow_mapping) | **DELETE** /rest/api/3/workflowscheme/{id}/workflow | Delete issue types for workflow in workflow scheme
[**delete_workflow_scheme**](WorkflowSchemesApi.md#delete_workflow_scheme) | **DELETE** /rest/api/3/workflowscheme/{id} | Delete workflow scheme
[**delete_workflow_scheme_issue_type**](WorkflowSchemesApi.md#delete_workflow_scheme_issue_type) | **DELETE** /rest/api/3/workflowscheme/{id}/issuetype/{issueType} | Delete workflow for issue type in workflow scheme
[**get_all_workflow_schemes**](WorkflowSchemesApi.md#get_all_workflow_schemes) | **GET** /rest/api/3/workflowscheme | Get all workflow schemes
[**get_default_workflow**](WorkflowSchemesApi.md#get_default_workflow) | **GET** /rest/api/3/workflowscheme/{id}/default | Get default workflow
[**get_project_usages_for_workflow_scheme**](WorkflowSchemesApi.md#get_project_usages_for_workflow_scheme) | **GET** /rest/api/3/workflowscheme/{workflowSchemeId}/projectUsages | Get projects which are using a given workflow scheme
[**get_workflow**](WorkflowSchemesApi.md#get_workflow) | **GET** /rest/api/3/workflowscheme/{id}/workflow | Get issue types for workflows in workflow scheme
[**get_workflow_scheme**](WorkflowSchemesApi.md#get_workflow_scheme) | **GET** /rest/api/3/workflowscheme/{id} | Get workflow scheme
[**get_workflow_scheme_issue_type**](WorkflowSchemesApi.md#get_workflow_scheme_issue_type) | **GET** /rest/api/3/workflowscheme/{id}/issuetype/{issueType} | Get workflow for issue type in workflow scheme
[**read_workflow_schemes**](WorkflowSchemesApi.md#read_workflow_schemes) | **POST** /rest/api/3/workflowscheme/read | Bulk get workflow schemes
[**set_workflow_scheme_issue_type**](WorkflowSchemesApi.md#set_workflow_scheme_issue_type) | **PUT** /rest/api/3/workflowscheme/{id}/issuetype/{issueType} | Set workflow for issue type in workflow scheme
[**update_default_workflow**](WorkflowSchemesApi.md#update_default_workflow) | **PUT** /rest/api/3/workflowscheme/{id}/default | Update default workflow
[**update_schemes**](WorkflowSchemesApi.md#update_schemes) | **POST** /rest/api/3/workflowscheme/update | Update workflow scheme
[**update_workflow_mapping**](WorkflowSchemesApi.md#update_workflow_mapping) | **PUT** /rest/api/3/workflowscheme/{id}/workflow | Set issue types for workflow in workflow scheme
[**update_workflow_scheme**](WorkflowSchemesApi.md#update_workflow_scheme) | **PUT** /rest/api/3/workflowscheme/{id} | Classic update workflow scheme
[**update_workflow_scheme_mappings**](WorkflowSchemesApi.md#update_workflow_scheme_mappings) | **POST** /rest/api/3/workflowscheme/update/mappings | Get required status mappings for workflow scheme update

# **create_workflow_scheme**
> WorkflowScheme create_workflow_scheme(body)

Create workflow scheme

Creates a workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowScheme() # WorkflowScheme | 

try:
    # Create workflow scheme
    api_response = api_instance.create_workflow_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->create_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowScheme**](WorkflowScheme.md)|  | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_default_workflow**
> WorkflowScheme delete_default_workflow(id, update_draft_if_needed=update_draft_if_needed)

Delete default workflow

Resets the default workflow for a workflow scheme. That is, the default workflow is set to Jira's system workflow (the *jira* workflow).  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` and a draft workflow scheme is created or updated with the default workflow reset. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
update_draft_if_needed = true # bool | Set to true to create or update the draft of a workflow scheme and delete the mapping from the draft, when the workflow scheme cannot be edited. Defaults to `false`. (optional)

try:
    # Delete default workflow
    api_response = api_instance.delete_default_workflow(id, update_draft_if_needed=update_draft_if_needed)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->delete_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **update_draft_if_needed** | **bool**| Set to true to create or update the draft of a workflow scheme and delete the mapping from the draft, when the workflow scheme cannot be edited. Defaults to &#x60;false&#x60;. | [optional] 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_workflow_mapping**
> delete_workflow_mapping(id, workflow_name, update_draft_if_needed=update_draft_if_needed)

Delete issue types for workflow in workflow scheme

Deletes the workflow-issue type mapping for a workflow in a workflow scheme.  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` and a draft workflow scheme is created or updated with the workflow-issue type mapping deleted. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
workflow_name = 'workflow_name_example' # str | The name of the workflow.
update_draft_if_needed = false # bool | Set to true to create or update the draft of a workflow scheme and delete the mapping from the draft, when the workflow scheme cannot be edited. Defaults to `false`. (optional) (default to false)

try:
    # Delete issue types for workflow in workflow scheme
    api_instance.delete_workflow_mapping(id, workflow_name, update_draft_if_needed=update_draft_if_needed)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->delete_workflow_mapping: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **workflow_name** | **str**| The name of the workflow. | 
 **update_draft_if_needed** | **bool**| Set to true to create or update the draft of a workflow scheme and delete the mapping from the draft, when the workflow scheme cannot be edited. Defaults to &#x60;false&#x60;. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_workflow_scheme**
> object delete_workflow_scheme(id)

Delete workflow scheme

Deletes a workflow scheme. Note that a workflow scheme cannot be deleted if it is active (that is, being used by at least one project).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as `schemeId`. For example, *schemeId=10301*.

try:
    # Delete workflow scheme
    api_response = api_instance.delete_workflow_scheme(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->delete_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as &#x60;schemeId&#x60;. For example, *schemeId&#x3D;10301*. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_workflow_scheme_issue_type**
> WorkflowScheme delete_workflow_scheme_issue_type(id, issue_type, update_draft_if_needed=update_draft_if_needed)

Delete workflow for issue type in workflow scheme

Deletes the issue type-workflow mapping for an issue type in a workflow scheme.  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` and a draft workflow scheme is created or updated with the issue type-workflow mapping deleted. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
issue_type = 'issue_type_example' # str | The ID of the issue type.
update_draft_if_needed = false # bool | Set to true to create or update the draft of a workflow scheme and update the mapping in the draft, when the workflow scheme cannot be edited. Defaults to `false`. (optional) (default to false)

try:
    # Delete workflow for issue type in workflow scheme
    api_response = api_instance.delete_workflow_scheme_issue_type(id, issue_type, update_draft_if_needed=update_draft_if_needed)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->delete_workflow_scheme_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **issue_type** | **str**| The ID of the issue type. | 
 **update_draft_if_needed** | **bool**| Set to true to create or update the draft of a workflow scheme and update the mapping in the draft, when the workflow scheme cannot be edited. Defaults to &#x60;false&#x60;. | [optional] [default to false]

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_workflow_schemes**
> PageBeanWorkflowScheme get_all_workflow_schemes(start_at=start_at, max_results=max_results)

Get all workflow schemes

Returns a [paginated](#pagination) list of all workflow schemes, not including draft workflow schemes.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get all workflow schemes
    api_response = api_instance.get_all_workflow_schemes(start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_all_workflow_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageBeanWorkflowScheme**](PageBeanWorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_default_workflow**
> DefaultWorkflow get_default_workflow(id, return_draft_if_exists=return_draft_if_exists)

Get default workflow

Returns the default workflow for a workflow scheme. The default workflow is the workflow that is assigned any issue types that have not been mapped to any other workflow. The default workflow has *All Unassigned Issue Types* listed in its issue types for the workflow scheme in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
return_draft_if_exists = false # bool | Set to `true` to return the default workflow for the workflow scheme's draft rather than scheme itself. If the workflow scheme does not have a draft, then the default workflow for the workflow scheme is returned. (optional) (default to false)

try:
    # Get default workflow
    api_response = api_instance.get_default_workflow(id, return_draft_if_exists=return_draft_if_exists)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **return_draft_if_exists** | **bool**| Set to &#x60;true&#x60; to return the default workflow for the workflow scheme&#x27;s draft rather than scheme itself. If the workflow scheme does not have a draft, then the default workflow for the workflow scheme is returned. | [optional] [default to false]

### Return type

[**DefaultWorkflow**](DefaultWorkflow.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_project_usages_for_workflow_scheme**
> WorkflowSchemeProjectUsageDTO get_project_usages_for_workflow_scheme(workflow_scheme_id, next_page_token=next_page_token, max_results=max_results)

Get projects which are using a given workflow scheme

Returns a page of projects using a given workflow scheme.

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
workflow_scheme_id = 'workflow_scheme_id_example' # str | The workflow scheme ID
next_page_token = 'next_page_token_example' # str | The cursor for pagination (optional)
max_results = 50 # int | The maximum number of results to return. Must be an integer between 1 and 200. (optional) (default to 50)

try:
    # Get projects which are using a given workflow scheme
    api_response = api_instance.get_project_usages_for_workflow_scheme(workflow_scheme_id, next_page_token=next_page_token, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_project_usages_for_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **workflow_scheme_id** | **str**| The workflow scheme ID | 
 **next_page_token** | **str**| The cursor for pagination | [optional] 
 **max_results** | **int**| The maximum number of results to return. Must be an integer between 1 and 200. | [optional] [default to 50]

### Return type

[**WorkflowSchemeProjectUsageDTO**](WorkflowSchemeProjectUsageDTO.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow**
> IssueTypesWorkflowMapping get_workflow(id, workflow_name=workflow_name, return_draft_if_exists=return_draft_if_exists)

Get issue types for workflows in workflow scheme

Returns the workflow-issue type mappings for a workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
workflow_name = 'workflow_name_example' # str | The name of a workflow in the scheme. Limits the results to the workflow-issue type mapping for the specified workflow. (optional)
return_draft_if_exists = false # bool | Returns the mapping from the workflow scheme's draft rather than the workflow scheme, if set to true. If no draft exists, the mapping from the workflow scheme is returned. (optional) (default to false)

try:
    # Get issue types for workflows in workflow scheme
    api_response = api_instance.get_workflow(id, workflow_name=workflow_name, return_draft_if_exists=return_draft_if_exists)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **workflow_name** | **str**| The name of a workflow in the scheme. Limits the results to the workflow-issue type mapping for the specified workflow. | [optional] 
 **return_draft_if_exists** | **bool**| Returns the mapping from the workflow scheme&#x27;s draft rather than the workflow scheme, if set to true. If no draft exists, the mapping from the workflow scheme is returned. | [optional] [default to false]

### Return type

[**IssueTypesWorkflowMapping**](IssueTypesWorkflowMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_scheme**
> WorkflowScheme get_workflow_scheme(id, return_draft_if_exists=return_draft_if_exists)

Get workflow scheme

Returns a workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as `schemeId`. For example, *schemeId=10301*.
return_draft_if_exists = false # bool | Returns the workflow scheme's draft rather than scheme itself, if set to true. If the workflow scheme does not have a draft, then the workflow scheme is returned. (optional) (default to false)

try:
    # Get workflow scheme
    api_response = api_instance.get_workflow_scheme(id, return_draft_if_exists=return_draft_if_exists)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as &#x60;schemeId&#x60;. For example, *schemeId&#x3D;10301*. | 
 **return_draft_if_exists** | **bool**| Returns the workflow scheme&#x27;s draft rather than scheme itself, if set to true. If the workflow scheme does not have a draft, then the workflow scheme is returned. | [optional] [default to false]

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_scheme_issue_type**
> IssueTypeWorkflowMapping get_workflow_scheme_issue_type(id, issue_type, return_draft_if_exists=return_draft_if_exists)

Get workflow for issue type in workflow scheme

Returns the issue type-workflow mapping for an issue type in a workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme.
issue_type = 'issue_type_example' # str | The ID of the issue type.
return_draft_if_exists = false # bool | Returns the mapping from the workflow scheme's draft rather than the workflow scheme, if set to true. If no draft exists, the mapping from the workflow scheme is returned. (optional) (default to false)

try:
    # Get workflow for issue type in workflow scheme
    api_response = api_instance.get_workflow_scheme_issue_type(id, issue_type, return_draft_if_exists=return_draft_if_exists)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->get_workflow_scheme_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme. | 
 **issue_type** | **str**| The ID of the issue type. | 
 **return_draft_if_exists** | **bool**| Returns the mapping from the workflow scheme&#x27;s draft rather than the workflow scheme, if set to true. If no draft exists, the mapping from the workflow scheme is returned. | [optional] [default to false]

### Return type

[**IssueTypeWorkflowMapping**](IssueTypeWorkflowMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **read_workflow_schemes**
> list[WorkflowSchemeReadResponse] read_workflow_schemes(body)

Bulk get workflow schemes

Returns a list of workflow schemes by providing workflow scheme IDs or project IDs.  **[Permissions](#permissions) required:**   *  *Administer Jira* global permission to access all, including project-scoped, workflow schemes  *  *Administer projects* project permissions to access project-scoped workflow schemes

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowSchemeReadRequest() # WorkflowSchemeReadRequest | 

try:
    # Bulk get workflow schemes
    api_response = api_instance.read_workflow_schemes(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->read_workflow_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowSchemeReadRequest**](WorkflowSchemeReadRequest.md)|  | 

### Return type

[**list[WorkflowSchemeReadResponse]**](WorkflowSchemeReadResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_workflow_scheme_issue_type**
> WorkflowScheme set_workflow_scheme_issue_type(body, id, issue_type)

Set workflow for issue type in workflow scheme

Sets the workflow for an issue type in a workflow scheme.  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` in the request body and a draft workflow scheme is created or updated with the new issue type-workflow mapping. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeWorkflowMapping() # IssueTypeWorkflowMapping | The issue type-project mapping.
id = 789 # int | The ID of the workflow scheme.
issue_type = 'issue_type_example' # str | The ID of the issue type.

try:
    # Set workflow for issue type in workflow scheme
    api_response = api_instance.set_workflow_scheme_issue_type(body, id, issue_type)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->set_workflow_scheme_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeWorkflowMapping**](IssueTypeWorkflowMapping.md)| The issue type-project mapping. | 
 **id** | **int**| The ID of the workflow scheme. | 
 **issue_type** | **str**| The ID of the issue type. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_default_workflow**
> WorkflowScheme update_default_workflow(body, id)

Update default workflow

Sets the default workflow for a workflow scheme.  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` in the request object and a draft workflow scheme is created or updated with the new default workflow. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.DefaultWorkflow() # DefaultWorkflow | The new default workflow.
id = 789 # int | The ID of the workflow scheme.

try:
    # Update default workflow
    api_response = api_instance.update_default_workflow(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->update_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DefaultWorkflow**](DefaultWorkflow.md)| The new default workflow. | 
 **id** | **int**| The ID of the workflow scheme. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_schemes**
> object update_schemes(body)

Update workflow scheme

Updates company-managed and team-managed project workflow schemes. This API doesn't have a concept of draft, so any changes made to a workflow scheme are immediately available. When changing the available statuses for issue types, an [asynchronous task](#async) migrates the issues as defined in the provided mappings.  **[Permissions](#permissions) required:**   *  *Administer Jira* project permission to update all, including global-scoped, workflow schemes.  *  *Administer projects* project permission to update project-scoped workflow schemes.

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = {
  "defaultWorkflowId" : "3e59db0f-ed6c-47ce-8d50-80c0c4572677",
  "description" : "description",
  "id" : "10000",
  "name" : "name",
  "statusMappingsByIssueTypeOverride" : [ {
    "issueTypeId" : "10001",
    "statusMappings" : [ {
      "newStatusId" : "2",
      "oldStatusId" : "1"
    }, {
      "newStatusId" : "4",
      "oldStatusId" : "3"
    } ]
  }, {
    "issueTypeId" : "10002",
    "statusMappings" : [ {
      "newStatusId" : "4",
      "oldStatusId" : "1"
    }, {
      "newStatusId" : "2",
      "oldStatusId" : "3"
    } ]
  } ],
  "statusMappingsByWorkflows" : [ {
    "newWorkflowId" : "3e59db0f-ed6c-47ce-8d50-80c0c4572677",
    "oldWorkflowId" : "3e59db0f-ed6c-47ce-8d50-80c0c4572677",
    "statusMappings" : [ {
      "newStatusId" : "2",
      "oldStatusId" : "1"
    }, {
      "newStatusId" : "4",
      "oldStatusId" : "3"
    } ]
  } ],
  "version" : {
    "id" : "527213fc-bc72-400f-aae0-df8d88db2c8a",
    "versionNumber" : 1
  },
  "workflowsForIssueTypes" : [ {
    "issueTypeIds" : [ "10000", "10003" ],
    "workflowId" : "3e59db0f-ed6c-47ce-8d50-80c0c4572677"
  }, {
    "issueTypeIds" : [ "10001`", "10002" ],
    "workflowId" : "3f83dg2a-ns2n-56ab-9812-42h5j1461629"
  } ]
} # dict(str, object) | 

try:
    # Update workflow scheme
    api_response = api_instance.update_schemes(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->update_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow_mapping**
> WorkflowScheme update_workflow_mapping(body, workflow_name, id)

Set issue types for workflow in workflow scheme

Sets the issue types for a workflow in a workflow scheme. The workflow can also be set as the default workflow for the workflow scheme. Unmapped issues types are mapped to the default workflow.  Note that active workflow schemes cannot be edited. If the workflow scheme is active, set `updateDraftIfNeeded` to `true` in the request body and a draft workflow scheme is created or updated with the new workflow-issue types mappings. The draft workflow scheme can be published in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypesWorkflowMapping() # IssueTypesWorkflowMapping | 
workflow_name = 'workflow_name_example' # str | The name of the workflow.
id = 789 # int | The ID of the workflow scheme.

try:
    # Set issue types for workflow in workflow scheme
    api_response = api_instance.update_workflow_mapping(body, workflow_name, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->update_workflow_mapping: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypesWorkflowMapping**](IssueTypesWorkflowMapping.md)|  | 
 **workflow_name** | **str**| The name of the workflow. | 
 **id** | **int**| The ID of the workflow scheme. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow_scheme**
> WorkflowScheme update_workflow_scheme(body, id)

Classic update workflow scheme

Updates a company-manged project workflow scheme, including the name, default workflow, issue type to project mappings, and more. If the workflow scheme is active (that is, being used by at least one project), then a draft workflow scheme is created or updated instead, provided that `updateDraftIfNeeded` is set to `true`.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowScheme() # WorkflowScheme | 
id = 789 # int | The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as `schemeId`. For example, *schemeId=10301*.

try:
    # Classic update workflow scheme
    api_response = api_instance.update_workflow_scheme(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->update_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowScheme**](WorkflowScheme.md)|  | 
 **id** | **int**| The ID of the workflow scheme. Find this ID by editing the desired workflow scheme in Jira. The ID is shown in the URL as &#x60;schemeId&#x60;. For example, *schemeId&#x3D;10301*. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow_scheme_mappings**
> WorkflowSchemeUpdateRequiredMappingsResponse update_workflow_scheme_mappings(body)

Get required status mappings for workflow scheme update

Gets the required status mappings for the desired changes to a workflow scheme. The results are provided per issue type and workflow. When updating a workflow scheme, status mappings can be provided per issue type, per workflow, or both.  **[Permissions](#permissions) required:**   *  *Administer Jira* permission to update all, including global-scoped, workflow schemes.  *  *Administer projects* project permission to update project-scoped workflow schemes.

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
api_instance = jira_client.WorkflowSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowSchemeUpdateRequiredMappingsRequest() # WorkflowSchemeUpdateRequiredMappingsRequest | 

try:
    # Get required status mappings for workflow scheme update
    api_response = api_instance.update_workflow_scheme_mappings(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemesApi->update_workflow_scheme_mappings: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowSchemeUpdateRequiredMappingsRequest**](WorkflowSchemeUpdateRequiredMappingsRequest.md)|  | 

### Return type

[**WorkflowSchemeUpdateRequiredMappingsResponse**](WorkflowSchemeUpdateRequiredMappingsResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

