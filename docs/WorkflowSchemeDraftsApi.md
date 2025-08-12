# jira_client.WorkflowSchemeDraftsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_workflow_scheme_draft_from_parent**](WorkflowSchemeDraftsApi.md#create_workflow_scheme_draft_from_parent) | **POST** /rest/api/3/workflowscheme/{id}/createdraft | Create draft workflow scheme
[**delete_draft_default_workflow**](WorkflowSchemeDraftsApi.md#delete_draft_default_workflow) | **DELETE** /rest/api/3/workflowscheme/{id}/draft/default | Delete draft default workflow
[**delete_draft_workflow_mapping**](WorkflowSchemeDraftsApi.md#delete_draft_workflow_mapping) | **DELETE** /rest/api/3/workflowscheme/{id}/draft/workflow | Delete issue types for workflow in draft workflow scheme
[**delete_workflow_scheme_draft**](WorkflowSchemeDraftsApi.md#delete_workflow_scheme_draft) | **DELETE** /rest/api/3/workflowscheme/{id}/draft | Delete draft workflow scheme
[**delete_workflow_scheme_draft_issue_type**](WorkflowSchemeDraftsApi.md#delete_workflow_scheme_draft_issue_type) | **DELETE** /rest/api/3/workflowscheme/{id}/draft/issuetype/{issueType} | Delete workflow for issue type in draft workflow scheme
[**get_draft_default_workflow**](WorkflowSchemeDraftsApi.md#get_draft_default_workflow) | **GET** /rest/api/3/workflowscheme/{id}/draft/default | Get draft default workflow
[**get_draft_workflow**](WorkflowSchemeDraftsApi.md#get_draft_workflow) | **GET** /rest/api/3/workflowscheme/{id}/draft/workflow | Get issue types for workflows in draft workflow scheme
[**get_workflow_scheme_draft**](WorkflowSchemeDraftsApi.md#get_workflow_scheme_draft) | **GET** /rest/api/3/workflowscheme/{id}/draft | Get draft workflow scheme
[**get_workflow_scheme_draft_issue_type**](WorkflowSchemeDraftsApi.md#get_workflow_scheme_draft_issue_type) | **GET** /rest/api/3/workflowscheme/{id}/draft/issuetype/{issueType} | Get workflow for issue type in draft workflow scheme
[**publish_draft_workflow_scheme**](WorkflowSchemeDraftsApi.md#publish_draft_workflow_scheme) | **POST** /rest/api/3/workflowscheme/{id}/draft/publish | Publish draft workflow scheme
[**set_workflow_scheme_draft_issue_type**](WorkflowSchemeDraftsApi.md#set_workflow_scheme_draft_issue_type) | **PUT** /rest/api/3/workflowscheme/{id}/draft/issuetype/{issueType} | Set workflow for issue type in draft workflow scheme
[**update_draft_default_workflow**](WorkflowSchemeDraftsApi.md#update_draft_default_workflow) | **PUT** /rest/api/3/workflowscheme/{id}/draft/default | Update draft default workflow
[**update_draft_workflow_mapping**](WorkflowSchemeDraftsApi.md#update_draft_workflow_mapping) | **PUT** /rest/api/3/workflowscheme/{id}/draft/workflow | Set issue types for workflow in workflow scheme
[**update_workflow_scheme_draft**](WorkflowSchemeDraftsApi.md#update_workflow_scheme_draft) | **PUT** /rest/api/3/workflowscheme/{id}/draft | Update draft workflow scheme

# **create_workflow_scheme_draft_from_parent**
> WorkflowScheme create_workflow_scheme_draft_from_parent(id)

Create draft workflow scheme

Create a draft workflow scheme from an active workflow scheme, by copying the active workflow scheme. Note that an active workflow scheme can only have one draft workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the active workflow scheme that the draft is created from.

try:
    # Create draft workflow scheme
    api_response = api_instance.create_workflow_scheme_draft_from_parent(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->create_workflow_scheme_draft_from_parent: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the active workflow scheme that the draft is created from. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_draft_default_workflow**
> WorkflowScheme delete_draft_default_workflow(id)

Delete draft default workflow

Resets the default workflow for a workflow scheme's draft. That is, the default workflow is set to Jira's system workflow (the *jira* workflow).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.

try:
    # Delete draft default workflow
    api_response = api_instance.delete_draft_default_workflow(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->delete_draft_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_draft_workflow_mapping**
> delete_draft_workflow_mapping(id, workflow_name)

Delete issue types for workflow in draft workflow scheme

Deletes the workflow-issue type mapping for a workflow in a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
workflow_name = 'workflow_name_example' # str | The name of the workflow.

try:
    # Delete issue types for workflow in draft workflow scheme
    api_instance.delete_draft_workflow_mapping(id, workflow_name)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->delete_draft_workflow_mapping: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **workflow_name** | **str**| The name of the workflow. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_workflow_scheme_draft**
> delete_workflow_scheme_draft(id)

Delete draft workflow scheme

Deletes a draft workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the active workflow scheme that the draft was created from.

try:
    # Delete draft workflow scheme
    api_instance.delete_workflow_scheme_draft(id)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->delete_workflow_scheme_draft: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the active workflow scheme that the draft was created from. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_workflow_scheme_draft_issue_type**
> WorkflowScheme delete_workflow_scheme_draft_issue_type(id, issue_type)

Delete workflow for issue type in draft workflow scheme

Deletes the issue type-workflow mapping for an issue type in a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
issue_type = 'issue_type_example' # str | The ID of the issue type.

try:
    # Delete workflow for issue type in draft workflow scheme
    api_response = api_instance.delete_workflow_scheme_draft_issue_type(id, issue_type)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->delete_workflow_scheme_draft_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **issue_type** | **str**| The ID of the issue type. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_draft_default_workflow**
> DefaultWorkflow get_draft_default_workflow(id)

Get draft default workflow

Returns the default workflow for a workflow scheme's draft. The default workflow is the workflow that is assigned any issue types that have not been mapped to any other workflow. The default workflow has *All Unassigned Issue Types* listed in its issue types for the workflow scheme in Jira.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.

try:
    # Get draft default workflow
    api_response = api_instance.get_draft_default_workflow(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->get_draft_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 

### Return type

[**DefaultWorkflow**](DefaultWorkflow.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_draft_workflow**
> IssueTypesWorkflowMapping get_draft_workflow(id, workflow_name=workflow_name)

Get issue types for workflows in draft workflow scheme

Returns the workflow-issue type mappings for a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
workflow_name = 'workflow_name_example' # str | The name of a workflow in the scheme. Limits the results to the workflow-issue type mapping for the specified workflow. (optional)

try:
    # Get issue types for workflows in draft workflow scheme
    api_response = api_instance.get_draft_workflow(id, workflow_name=workflow_name)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->get_draft_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **workflow_name** | **str**| The name of a workflow in the scheme. Limits the results to the workflow-issue type mapping for the specified workflow. | [optional] 

### Return type

[**IssueTypesWorkflowMapping**](IssueTypesWorkflowMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_scheme_draft**
> WorkflowScheme get_workflow_scheme_draft(id)

Get draft workflow scheme

Returns the draft workflow scheme for an active workflow scheme. Draft workflow schemes allow changes to be made to the active workflow schemes: When an active workflow scheme is updated, a draft copy is created. The draft is modified, then the changes in the draft are copied back to the active workflow scheme. See [Configuring workflow schemes](https://confluence.atlassian.com/x/tohKLg) for more information.   Note that:   *  Only active workflow schemes can have draft workflow schemes.  *  An active workflow scheme can only have one draft workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the active workflow scheme that the draft was created from.

try:
    # Get draft workflow scheme
    api_response = api_instance.get_workflow_scheme_draft(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->get_workflow_scheme_draft: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the active workflow scheme that the draft was created from. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_scheme_draft_issue_type**
> IssueTypeWorkflowMapping get_workflow_scheme_draft_issue_type(id, issue_type)

Get workflow for issue type in draft workflow scheme

Returns the issue type-workflow mapping for an issue type in a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
issue_type = 'issue_type_example' # str | The ID of the issue type.

try:
    # Get workflow for issue type in draft workflow scheme
    api_response = api_instance.get_workflow_scheme_draft_issue_type(id, issue_type)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->get_workflow_scheme_draft_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **issue_type** | **str**| The ID of the issue type. | 

### Return type

[**IssueTypeWorkflowMapping**](IssueTypeWorkflowMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **publish_draft_workflow_scheme**
> publish_draft_workflow_scheme(body, id, validate_only=validate_only)

Publish draft workflow scheme

Publishes a draft workflow scheme.  Where the draft workflow includes new workflow statuses for an issue type, mappings are provided to update issues with the original workflow status to the new workflow status.  This operation is [asynchronous](#async). Follow the `location` link in the response to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain updates.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
body = jira_client.PublishDraftWorkflowScheme() # PublishDraftWorkflowScheme | Details of the status mappings.
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
validate_only = false # bool | Whether the request only performs a validation. (optional) (default to false)

try:
    # Publish draft workflow scheme
    api_instance.publish_draft_workflow_scheme(body, id, validate_only=validate_only)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->publish_draft_workflow_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**PublishDraftWorkflowScheme**](PublishDraftWorkflowScheme.md)| Details of the status mappings. | 
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **validate_only** | **bool**| Whether the request only performs a validation. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_workflow_scheme_draft_issue_type**
> WorkflowScheme set_workflow_scheme_draft_issue_type(body, id, issue_type)

Set workflow for issue type in draft workflow scheme

Sets the workflow for an issue type in a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypeWorkflowMapping() # IssueTypeWorkflowMapping | The issue type-project mapping.
id = 789 # int | The ID of the workflow scheme that the draft belongs to.
issue_type = 'issue_type_example' # str | The ID of the issue type.

try:
    # Set workflow for issue type in draft workflow scheme
    api_response = api_instance.set_workflow_scheme_draft_issue_type(body, id, issue_type)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->set_workflow_scheme_draft_issue_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypeWorkflowMapping**](IssueTypeWorkflowMapping.md)| The issue type-project mapping. | 
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 
 **issue_type** | **str**| The ID of the issue type. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_draft_default_workflow**
> WorkflowScheme update_draft_default_workflow(body, id)

Update draft default workflow

Sets the default workflow for a workflow scheme's draft.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
body = jira_client.DefaultWorkflow() # DefaultWorkflow | The object for the new default workflow.
id = 789 # int | The ID of the workflow scheme that the draft belongs to.

try:
    # Update draft default workflow
    api_response = api_instance.update_draft_default_workflow(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->update_draft_default_workflow: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DefaultWorkflow**](DefaultWorkflow.md)| The object for the new default workflow. | 
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_draft_workflow_mapping**
> WorkflowScheme update_draft_workflow_mapping(body, workflow_name, id)

Set issue types for workflow in workflow scheme

Sets the issue types for a workflow in a workflow scheme's draft. The workflow can also be set as the default workflow for the draft workflow scheme. Unmapped issues types are mapped to the default workflow.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueTypesWorkflowMapping() # IssueTypesWorkflowMapping | 
workflow_name = 'workflow_name_example' # str | The name of the workflow.
id = 789 # int | The ID of the workflow scheme that the draft belongs to.

try:
    # Set issue types for workflow in workflow scheme
    api_response = api_instance.update_draft_workflow_mapping(body, workflow_name, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->update_draft_workflow_mapping: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueTypesWorkflowMapping**](IssueTypesWorkflowMapping.md)|  | 
 **workflow_name** | **str**| The name of the workflow. | 
 **id** | **int**| The ID of the workflow scheme that the draft belongs to. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow_scheme_draft**
> WorkflowScheme update_workflow_scheme_draft(body, id)

Update draft workflow scheme

Updates a draft workflow scheme. If a draft workflow scheme does not exist for the active workflow scheme, then a draft is created. Note that an active workflow scheme can only have one draft workflow scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.WorkflowSchemeDraftsApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowScheme() # WorkflowScheme | 
id = 789 # int | The ID of the active workflow scheme that the draft was created from.

try:
    # Update draft workflow scheme
    api_response = api_instance.update_workflow_scheme_draft(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowSchemeDraftsApi->update_workflow_scheme_draft: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowScheme**](WorkflowScheme.md)|  | 
 **id** | **int**| The ID of the active workflow scheme that the draft was created from. | 

### Return type

[**WorkflowScheme**](WorkflowScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

