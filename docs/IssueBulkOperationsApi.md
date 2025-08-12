# jira_client.IssueBulkOperationsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_available_transitions**](IssueBulkOperationsApi.md#get_available_transitions) | **GET** /rest/api/3/bulk/issues/transition | Get available transitions
[**get_bulk_editable_fields**](IssueBulkOperationsApi.md#get_bulk_editable_fields) | **GET** /rest/api/3/bulk/issues/fields | Get bulk editable fields
[**get_bulk_operation_progress**](IssueBulkOperationsApi.md#get_bulk_operation_progress) | **GET** /rest/api/3/bulk/queue/{taskId} | Get bulk issue operation progress
[**submit_bulk_delete**](IssueBulkOperationsApi.md#submit_bulk_delete) | **POST** /rest/api/3/bulk/issues/delete | Bulk delete issues
[**submit_bulk_edit**](IssueBulkOperationsApi.md#submit_bulk_edit) | **POST** /rest/api/3/bulk/issues/fields | Bulk edit issues
[**submit_bulk_move**](IssueBulkOperationsApi.md#submit_bulk_move) | **POST** /rest/api/3/bulk/issues/move | Bulk move issues
[**submit_bulk_transition**](IssueBulkOperationsApi.md#submit_bulk_transition) | **POST** /rest/api/3/bulk/issues/transition | Bulk transition issue statuses
[**submit_bulk_unwatch**](IssueBulkOperationsApi.md#submit_bulk_unwatch) | **POST** /rest/api/3/bulk/issues/unwatch | Bulk unwatch issues
[**submit_bulk_watch**](IssueBulkOperationsApi.md#submit_bulk_watch) | **POST** /rest/api/3/bulk/issues/watch | Bulk watch issues

# **get_available_transitions**
> BulkTransitionGetAvailableTransitions get_available_transitions(issue_ids_or_keys, ending_before=ending_before, starting_after=starting_after)

Get available transitions

Use this API to retrieve a list of transitions available for the specified issues that can be used or bulk transition operations. You can submit either single or multiple issues in the query to obtain the available transitions.  The response will provide the available transitions for issues, organized by their respective workflows. **Only the transitions that are common among the issues within that workflow and do not involve any additional field updates will be included.** For bulk transitions that require additional field updates, please utilise the Jira Cloud UI.  You can request available transitions for up to 1,000 issues in a single operation. This API uses pagination to return responses, delivering 50 workflows at a time.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Transition [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/permissions-for-company-managed-projects/#Transition-issues/) in all projects that contain the selected issues.  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
issue_ids_or_keys = 'issue_ids_or_keys_example' # str | Comma (,) separated Ids or keys of the issues to get transitions available for them.
ending_before = 'ending_before_example' # str | (Optional)The end cursor for use in pagination. (optional)
starting_after = 'starting_after_example' # str | (Optional)The start cursor for use in pagination. (optional)

try:
    # Get available transitions
    api_response = api_instance.get_available_transitions(issue_ids_or_keys, ending_before=ending_before, starting_after=starting_after)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->get_available_transitions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_ids_or_keys** | **str**| Comma (,) separated Ids or keys of the issues to get transitions available for them. | 
 **ending_before** | **str**| (Optional)The end cursor for use in pagination. | [optional] 
 **starting_after** | **str**| (Optional)The start cursor for use in pagination. | [optional] 

### Return type

[**BulkTransitionGetAvailableTransitions**](BulkTransitionGetAvailableTransitions.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_bulk_editable_fields**
> BulkEditGetFields get_bulk_editable_fields(issue_ids_or_keys, search_text=search_text, ending_before=ending_before, starting_after=starting_after)

Get bulk editable fields

Use this API to get a list of fields visible to the user to perform bulk edit operations. You can pass single or multiple issues in the query to get eligible editable fields. This API uses pagination to return responses, delivering 50 fields at a time.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  Depending on the field, any field-specific permissions required to edit it.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
issue_ids_or_keys = 'issue_ids_or_keys_example' # str | The IDs or keys of the issues to get editable fields from.
search_text = 'search_text_example' # str | (Optional)The text to search for in the editable fields. (optional)
ending_before = 'ending_before_example' # str | (Optional)The end cursor for use in pagination. (optional)
starting_after = 'starting_after_example' # str | (Optional)The start cursor for use in pagination. (optional)

try:
    # Get bulk editable fields
    api_response = api_instance.get_bulk_editable_fields(issue_ids_or_keys, search_text=search_text, ending_before=ending_before, starting_after=starting_after)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->get_bulk_editable_fields: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_ids_or_keys** | **str**| The IDs or keys of the issues to get editable fields from. | 
 **search_text** | **str**| (Optional)The text to search for in the editable fields. | [optional] 
 **ending_before** | **str**| (Optional)The end cursor for use in pagination. | [optional] 
 **starting_after** | **str**| (Optional)The start cursor for use in pagination. | [optional] 

### Return type

[**BulkEditGetFields**](BulkEditGetFields.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_bulk_operation_progress**
> BulkOperationProgress get_bulk_operation_progress(task_id)

Get bulk issue operation progress

Use this to get the progress state for the specified bulk operation `taskId`.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  If the task is running, this resource will return:      {\"taskId\":\"10779\",\"status\":\"RUNNING\",\"progressPercent\":65,\"submittedBy\":{\"accountId\":\"5b10a2844c20165700ede21g\"},\"created\":1690180055963,\"started\":1690180056206,\"updated\":169018005829}  If the task has completed, then this resource will return:      {\"processedAccessibleIssues\":[10001,10002],\"created\":1709189449954,\"progressPercent\":100,\"started\":1709189450154,\"status\":\"COMPLETE\",\"submittedBy\":{\"accountId\":\"5b10a2844c20165700ede21g\"},\"invalidOrInaccessibleIssueCount\":0,\"taskId\":\"10000\",\"totalIssueCount\":2,\"updated\":1709189450354}  **Note:** You can view task progress for up to 14 days from creation.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
task_id = 'task_id_example' # str | The ID of the task.

try:
    # Get bulk issue operation progress
    api_response = api_instance.get_bulk_operation_progress(task_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->get_bulk_operation_progress: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **task_id** | **str**| The ID of the task. | 

### Return type

[**BulkOperationProgress**](BulkOperationProgress.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_delete**
> SubmittedBulkOperation submit_bulk_delete(body)

Bulk delete issues

Use this API to submit a bulk delete request. You can delete up to 1,000 issues in a single operation.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Delete [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/permissions-for-company-managed-projects/#Delete-issues/) in all projects that contain the selected issues.  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkDeletePayload() # IssueBulkDeletePayload | The request body containing the issues to be deleted.

try:
    # Bulk delete issues
    api_response = api_instance.submit_bulk_delete(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_delete: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkDeletePayload**](IssueBulkDeletePayload.md)| The request body containing the issues to be deleted. | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_edit**
> SubmittedBulkOperation submit_bulk_edit(body)

Bulk edit issues

Use this API to submit a bulk edit request and simultaneously edit multiple issues. There are limits applied to the number of issues and fields that can be edited. A single request can accommodate a maximum of 1000 issues (including subtasks) and 200 fields.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  Edit [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkEditPayload() # IssueBulkEditPayload | The request body containing the issues to be edited and the new field values.

try:
    # Bulk edit issues
    api_response = api_instance.submit_bulk_edit(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_edit: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkEditPayload**](IssueBulkEditPayload.md)| The request body containing the issues to be edited and the new field values. | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_move**
> SubmittedBulkOperation submit_bulk_move(body)

Bulk move issues

Use this API to submit a bulk issue move request. You can move multiple issues from multiple projects in a single request, but they must all be moved to a single project, issue type, and parent. You can't move more than 1000 issues (including subtasks) at once.  #### Scenarios: ####  This is an early version of the API and it doesn't have full feature parity with the Bulk Move UI experience.   *  Moving issue of type A to issue of type B in the same project or a different project: `SUPPORTED`  *  Moving multiple issues of type A in one or more projects to multiple issues of type B in one of the source projects or a different project: `SUPPORTED`  *  Moving issues of multiple issue types in one or more projects to issues of a single issue type in one of the source project or a different project: **`SUPPORTED`**       E.g. Moving issues of story and task issue types in project 1 and project 2 to issues of task issue type in project 3  *  Moving a standard parent issue of type A with its multiple subtask issue types in one project to standard issue of type B and multiple subtask issue types in the same project or a different project: `SUPPORTED`  *  Moving standard issues with their subtasks to a parent issue in the same project or a different project without losing their relation: `SUPPORTED`  *  Moving an epic issue with its child issues to a different project without losing their relation: `SUPPORTED`       This usecase is **supported using multiple requests**. Move the epic in one request and then move the children in a separate request with target parent set to the epic issue id              (Alternatively, move them individually and stitch the relationship back with the Bulk Edit API)  #### Limits applied to bulk issue moves: ####  When using the bulk move, keep in mind that there are limits on the number of issues and fields you can include.   *  You can move up to 1,000 issues in a single operation, including any subtasks.  *  The total combined number of fields across all issues must not exceed 1,500,000. For example, if each issue includes 15,000 fields, then the maximum number of issues that can be moved is 100.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Move [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in source projects.  *  Create [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in destination projects.  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in destination projects, if moving subtasks only.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkMovePayload() # IssueBulkMovePayload | 

try:
    # Bulk move issues
    api_response = api_instance.submit_bulk_move(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_move: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkMovePayload**](IssueBulkMovePayload.md)|  | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_transition**
> SubmittedBulkOperation submit_bulk_transition(body)

Bulk transition issue statuses

Use this API to submit a bulk issue status transition request. You can transition multiple issues, alongside with their valid transition Ids. You can transition up to 1,000 issues in a single operation.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Transition [issues permission](https://support.atlassian.com/jira-cloud-administration/docs/permissions-for-company-managed-projects/#Transition-issues/) in all projects that contain the selected issues.  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkTransitionPayload() # IssueBulkTransitionPayload | The request body containing the issues to be transitioned.

try:
    # Bulk transition issue statuses
    api_response = api_instance.submit_bulk_transition(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_transition: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkTransitionPayload**](IssueBulkTransitionPayload.md)| The request body containing the issues to be transitioned. | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_unwatch**
> SubmittedBulkOperation submit_bulk_unwatch(body)

Bulk unwatch issues

Use this API to submit a bulk unwatch request. You can unwatch up to 1,000 issues in a single operation.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkWatchOrUnwatchPayload() # IssueBulkWatchOrUnwatchPayload | The request body containing the issues to be unwatched.

try:
    # Bulk unwatch issues
    api_response = api_instance.submit_bulk_unwatch(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_unwatch: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkWatchOrUnwatchPayload**](IssueBulkWatchOrUnwatchPayload.md)| The request body containing the issues to be unwatched. | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **submit_bulk_watch**
> SubmittedBulkOperation submit_bulk_watch(body)

Bulk watch issues

Use this API to submit a bulk watch request. You can watch up to 1,000 issues in a single operation.  **[Permissions](#permissions) required:**   *  Global bulk change [permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-global-permissions/).  *  Browse [project permission](https://support.atlassian.com/jira-cloud-administration/docs/manage-project-permissions/) in all projects that contain the selected issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueBulkOperationsApi(jira_client.ApiClient(configuration))
body = jira_client.IssueBulkWatchOrUnwatchPayload() # IssueBulkWatchOrUnwatchPayload | The request body containing the issues to be watched.

try:
    # Bulk watch issues
    api_response = api_instance.submit_bulk_watch(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueBulkOperationsApi->submit_bulk_watch: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueBulkWatchOrUnwatchPayload**](IssueBulkWatchOrUnwatchPayload.md)| The request body containing the issues to be watched. | 

### Return type

[**SubmittedBulkOperation**](SubmittedBulkOperation.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

