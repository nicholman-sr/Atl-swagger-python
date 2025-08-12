# jira_client.IssueWorklogsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_worklog**](IssueWorklogsApi.md#add_worklog) | **POST** /rest/api/3/issue/{issueIdOrKey}/worklog | Add worklog
[**bulk_delete_worklogs**](IssueWorklogsApi.md#bulk_delete_worklogs) | **DELETE** /rest/api/3/issue/{issueIdOrKey}/worklog | Bulk delete worklogs
[**bulk_move_worklogs**](IssueWorklogsApi.md#bulk_move_worklogs) | **POST** /rest/api/3/issue/{issueIdOrKey}/worklog/move | Bulk move worklogs
[**delete_worklog**](IssueWorklogsApi.md#delete_worklog) | **DELETE** /rest/api/3/issue/{issueIdOrKey}/worklog/{id} | Delete worklog
[**get_ids_of_worklogs_deleted_since**](IssueWorklogsApi.md#get_ids_of_worklogs_deleted_since) | **GET** /rest/api/3/worklog/deleted | Get IDs of deleted worklogs
[**get_ids_of_worklogs_modified_since**](IssueWorklogsApi.md#get_ids_of_worklogs_modified_since) | **GET** /rest/api/3/worklog/updated | Get IDs of updated worklogs
[**get_issue_worklog**](IssueWorklogsApi.md#get_issue_worklog) | **GET** /rest/api/3/issue/{issueIdOrKey}/worklog | Get issue worklogs
[**get_worklog**](IssueWorklogsApi.md#get_worklog) | **GET** /rest/api/3/issue/{issueIdOrKey}/worklog/{id} | Get worklog
[**get_worklogs_for_ids**](IssueWorklogsApi.md#get_worklogs_for_ids) | **POST** /rest/api/3/worklog/list | Get worklogs
[**update_worklog**](IssueWorklogsApi.md#update_worklog) | **PUT** /rest/api/3/issue/{issueIdOrKey}/worklog/{id} | Update worklog

# **add_worklog**
> Worklog add_worklog(body, issue_id_or_key, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, reduce_by=reduce_by, expand=expand, override_editable_flag=override_editable_flag)

Add worklog

Adds a worklog to an issue.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Work on issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
body = {
  "comment" : {
    "content" : [ {
      "content" : [ {
        "text" : "I did some work here.",
        "type" : "text"
      } ],
      "type" : "paragraph"
    } ],
    "type" : "doc",
    "version" : 1
  },
  "started" : "2021-01-17T12:34:00.000+0000",
  "timeSpentSeconds" : 12000,
  "visibility" : {
    "identifier" : "276f955c-63d7-42c8-9520-92d01dca0625",
    "type" : "group"
  }
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key the issue.
notify_users = true # bool | Whether users watching the issue are notified by email. (optional) (default to true)
adjust_estimate = 'auto' # str | Defines how to update the issue's time estimate, the options are:   *  `new` Sets the estimate to a specific value, defined in `newEstimate`.  *  `leave` Leaves the estimate unchanged.  *  `manual` Reduces the estimate by amount specified in `reduceBy`.  *  `auto` Reduces the estimate by the value of `timeSpent` in the worklog. (optional) (default to auto)
new_estimate = 'new_estimate_example' # str | The value to set as the issue's remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when `adjustEstimate` is `new`. (optional)
reduce_by = 'reduce_by_example' # str | The amount to reduce the issue's remaining estimate by, as days (\\#d), hours (\\#h), or minutes (\\#m). For example, *2d*. Required when `adjustEstimate` is `manual`. (optional)
expand = '' # str | Use [expand](#expansion) to include additional information about work logs in the response. This parameter accepts `properties`, which returns worklog properties. (optional)
override_editable_flag = false # bool | Whether the worklog entry should be added to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) can use this flag. (optional) (default to false)

try:
    # Add worklog
    api_response = api_instance.add_worklog(body, issue_id_or_key, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, reduce_by=reduce_by, expand=expand, override_editable_flag=override_editable_flag)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->add_worklog: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key the issue. | 
 **notify_users** | **bool**| Whether users watching the issue are notified by email. | [optional] [default to true]
 **adjust_estimate** | **str**| Defines how to update the issue&#x27;s time estimate, the options are:   *  &#x60;new&#x60; Sets the estimate to a specific value, defined in &#x60;newEstimate&#x60;.  *  &#x60;leave&#x60; Leaves the estimate unchanged.  *  &#x60;manual&#x60; Reduces the estimate by amount specified in &#x60;reduceBy&#x60;.  *  &#x60;auto&#x60; Reduces the estimate by the value of &#x60;timeSpent&#x60; in the worklog. | [optional] [default to auto]
 **new_estimate** | **str**| The value to set as the issue&#x27;s remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when &#x60;adjustEstimate&#x60; is &#x60;new&#x60;. | [optional] 
 **reduce_by** | **str**| The amount to reduce the issue&#x27;s remaining estimate by, as days (\\#d), hours (\\#h), or minutes (\\#m). For example, *2d*. Required when &#x60;adjustEstimate&#x60; is &#x60;manual&#x60;. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about work logs in the response. This parameter accepts &#x60;properties&#x60;, which returns worklog properties. | [optional] 
 **override_editable_flag** | **bool**| Whether the worklog entry should be added to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) can use this flag. | [optional] [default to false]

### Return type

[**Worklog**](Worklog.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulk_delete_worklogs**
> bulk_delete_worklogs(body, issue_id_or_key, adjust_estimate=adjust_estimate, override_editable_flag=override_editable_flag)

Bulk delete worklogs

Deletes a list of worklogs from an issue. This is an experimental API with limitations:   *  You can't delete more than 5000 worklogs at once.  *  No notifications will be sent for deleted worklogs.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  *Delete all worklogs*[ project permission](https://confluence.atlassian.com/x/yodKLg) to delete any worklog.  *  If any worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
body = jira_client.WorklogIdsRequestBean() # WorklogIdsRequestBean | A JSON object containing a list of worklog IDs.
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
adjust_estimate = 'auto' # str | Defines how to update the issue's time estimate, the options are:   *  `leave` Leaves the estimate unchanged.  *  `auto` Reduces the estimate by the aggregate value of `timeSpent` across all worklogs being deleted. (optional) (default to auto)
override_editable_flag = false # bool | Whether the work log entries should be removed to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. (optional) (default to false)

try:
    # Bulk delete worklogs
    api_instance.bulk_delete_worklogs(body, issue_id_or_key, adjust_estimate=adjust_estimate, override_editable_flag=override_editable_flag)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->bulk_delete_worklogs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorklogIdsRequestBean**](WorklogIdsRequestBean.md)| A JSON object containing a list of worklog IDs. | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **adjust_estimate** | **str**| Defines how to update the issue&#x27;s time estimate, the options are:   *  &#x60;leave&#x60; Leaves the estimate unchanged.  *  &#x60;auto&#x60; Reduces the estimate by the aggregate value of &#x60;timeSpent&#x60; across all worklogs being deleted. | [optional] [default to auto]
 **override_editable_flag** | **bool**| Whether the work log entries should be removed to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulk_move_worklogs**
> bulk_move_worklogs(body, issue_id_or_key, adjust_estimate=adjust_estimate, override_editable_flag=override_editable_flag)

Bulk move worklogs

Moves a list of worklogs from one issue to another. This is an experimental API with several limitations:   *  You can't move more than 5000 worklogs at once.  *  You can't move worklogs containing an attachment.  *  You can't move worklogs restricted by project roles.  *  No notifications will be sent for moved worklogs.  *  No webhooks or events will be sent for moved worklogs.  *  No issue history will be recorded for moved worklogs.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the projects containing the source and destination issues.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  *Delete all worklogs*[ and *Edit all worklogs*](https://confluence.atlassian.com/x/yodKLg)[project permission](https://confluence.atlassian.com/x/yodKLg)  *  If the worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
body = jira_client.WorklogsMoveRequestBean() # WorklogsMoveRequestBean | A JSON object containing a list of worklog IDs and the ID or key of the destination issue.
issue_id_or_key = 'issue_id_or_key_example' # str | 
adjust_estimate = 'auto' # str | Defines how to update the issues' time estimate, the options are:   *  `leave` Leaves the estimate unchanged.  *  `auto` Reduces the estimate by the aggregate value of `timeSpent` across all worklogs being moved in the source issue, and increases it in the destination issue. (optional) (default to auto)
override_editable_flag = false # bool | Whether the work log entry should be moved to and from the issues even if the issues are not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. (optional) (default to false)

try:
    # Bulk move worklogs
    api_instance.bulk_move_worklogs(body, issue_id_or_key, adjust_estimate=adjust_estimate, override_editable_flag=override_editable_flag)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->bulk_move_worklogs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorklogsMoveRequestBean**](WorklogsMoveRequestBean.md)| A JSON object containing a list of worklog IDs and the ID or key of the destination issue. | 
 **issue_id_or_key** | **str**|  | 
 **adjust_estimate** | **str**| Defines how to update the issues&#x27; time estimate, the options are:   *  &#x60;leave&#x60; Leaves the estimate unchanged.  *  &#x60;auto&#x60; Reduces the estimate by the aggregate value of &#x60;timeSpent&#x60; across all worklogs being moved in the source issue, and increases it in the destination issue. | [optional] [default to auto]
 **override_editable_flag** | **bool**| Whether the work log entry should be moved to and from the issues even if the issues are not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_worklog**
> delete_worklog(issue_id_or_key, id, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, increase_by=increase_by, override_editable_flag=override_editable_flag)

Delete worklog

Deletes a worklog from an issue.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  *Delete all worklogs*[ project permission](https://confluence.atlassian.com/x/yodKLg) to delete any worklog or *Delete own worklogs* to delete worklogs created by the user,  *  If the worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
id = 'id_example' # str | The ID of the worklog.
notify_users = true # bool | Whether users watching the issue are notified by email. (optional) (default to true)
adjust_estimate = 'auto' # str | Defines how to update the issue's time estimate, the options are:   *  `new` Sets the estimate to a specific value, defined in `newEstimate`.  *  `leave` Leaves the estimate unchanged.  *  `manual` Increases the estimate by amount specified in `increaseBy`.  *  `auto` Reduces the estimate by the value of `timeSpent` in the worklog. (optional) (default to auto)
new_estimate = 'new_estimate_example' # str | The value to set as the issue's remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when `adjustEstimate` is `new`. (optional)
increase_by = 'increase_by_example' # str | The amount to increase the issue's remaining estimate by, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when `adjustEstimate` is `manual`. (optional)
override_editable_flag = false # bool | Whether the work log entry should be added to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. (optional) (default to false)

try:
    # Delete worklog
    api_instance.delete_worklog(issue_id_or_key, id, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, increase_by=increase_by, override_editable_flag=override_editable_flag)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->delete_worklog: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **id** | **str**| The ID of the worklog. | 
 **notify_users** | **bool**| Whether users watching the issue are notified by email. | [optional] [default to true]
 **adjust_estimate** | **str**| Defines how to update the issue&#x27;s time estimate, the options are:   *  &#x60;new&#x60; Sets the estimate to a specific value, defined in &#x60;newEstimate&#x60;.  *  &#x60;leave&#x60; Leaves the estimate unchanged.  *  &#x60;manual&#x60; Increases the estimate by amount specified in &#x60;increaseBy&#x60;.  *  &#x60;auto&#x60; Reduces the estimate by the value of &#x60;timeSpent&#x60; in the worklog. | [optional] [default to auto]
 **new_estimate** | **str**| The value to set as the issue&#x27;s remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when &#x60;adjustEstimate&#x60; is &#x60;new&#x60;. | [optional] 
 **increase_by** | **str**| The amount to increase the issue&#x27;s remaining estimate by, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when &#x60;adjustEstimate&#x60; is &#x60;manual&#x60;. | [optional] 
 **override_editable_flag** | **bool**| Whether the work log entry should be added to the issue even if the issue is not editable, because jira.issue.editable set to false or missing. For example, the issue is closed. Connect and Forge app users with admin permission can use this flag. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_ids_of_worklogs_deleted_since**
> ChangedWorklogs get_ids_of_worklogs_deleted_since(since=since)

Get IDs of deleted worklogs

Returns a list of IDs and delete timestamps for worklogs deleted after a date and time.  This resource is paginated, with a limit of 1000 worklogs per page. Each page lists worklogs from oldest to youngest. If the number of items in the date range exceeds 1000, `until` indicates the timestamp of the youngest item on the page. Also, `nextPage` provides the URL for the next page of worklogs. The `lastPage` parameter is set to true on the last page of worklogs.  This resource does not return worklogs deleted during the minute preceding the request.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
since = 0 # int | The date and time, as a UNIX timestamp in milliseconds, after which deleted worklogs are returned. (optional) (default to 0)

try:
    # Get IDs of deleted worklogs
    api_response = api_instance.get_ids_of_worklogs_deleted_since(since=since)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->get_ids_of_worklogs_deleted_since: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **since** | **int**| The date and time, as a UNIX timestamp in milliseconds, after which deleted worklogs are returned. | [optional] [default to 0]

### Return type

[**ChangedWorklogs**](ChangedWorklogs.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_ids_of_worklogs_modified_since**
> ChangedWorklogs get_ids_of_worklogs_modified_since(since=since, expand=expand)

Get IDs of updated worklogs

Returns a list of IDs and update timestamps for worklogs updated after a date and time.  This resource is paginated, with a limit of 1000 worklogs per page. Each page lists worklogs from oldest to youngest. If the number of items in the date range exceeds 1000, `until` indicates the timestamp of the youngest item on the page. Also, `nextPage` provides the URL for the next page of worklogs. The `lastPage` parameter is set to true on the last page of worklogs.  This resource does not return worklogs updated during the minute preceding the request.  **[Permissions](#permissions) required:** Permission to access Jira, however, worklogs are only returned where either of the following is true:   *  the worklog is set as *Viewable by All Users*.  *  the user is a member of a project role or group with permission to view the worklog.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
since = 0 # int | The date and time, as a UNIX timestamp in milliseconds, after which updated worklogs are returned. (optional) (default to 0)
expand = '' # str | Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts `properties` that returns the properties of each worklog. (optional)

try:
    # Get IDs of updated worklogs
    api_response = api_instance.get_ids_of_worklogs_modified_since(since=since, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->get_ids_of_worklogs_modified_since: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **since** | **int**| The date and time, as a UNIX timestamp in milliseconds, after which updated worklogs are returned. | [optional] [default to 0]
 **expand** | **str**| Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts &#x60;properties&#x60; that returns the properties of each worklog. | [optional] 

### Return type

[**ChangedWorklogs**](ChangedWorklogs.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_worklog**
> PageOfWorklogs get_issue_worklog(issue_id_or_key, start_at=start_at, max_results=max_results, started_after=started_after, started_before=started_before, expand=expand)

Get issue worklogs

Returns worklogs for an issue (ordered by created time), starting from the oldest worklog or from the worklog started on or after a date and time.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Workloads are only returned where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  If the worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 5000 # int | The maximum number of items to return per page. (optional) (default to 5000)
started_after = 789 # int | The worklog start date and time, as a UNIX timestamp in milliseconds, after which worklogs are returned. (optional)
started_before = 789 # int | The worklog start date and time, as a UNIX timestamp in milliseconds, before which worklogs are returned. (optional)
expand = '' # str | Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts`properties`, which returns worklog properties. (optional)

try:
    # Get issue worklogs
    api_response = api_instance.get_issue_worklog(issue_id_or_key, start_at=start_at, max_results=max_results, started_after=started_after, started_before=started_before, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->get_issue_worklog: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 5000]
 **started_after** | **int**| The worklog start date and time, as a UNIX timestamp in milliseconds, after which worklogs are returned. | [optional] 
 **started_before** | **int**| The worklog start date and time, as a UNIX timestamp in milliseconds, before which worklogs are returned. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts&#x60;properties&#x60;, which returns worklog properties. | [optional] 

### Return type

[**PageOfWorklogs**](PageOfWorklogs.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_worklog**
> Worklog get_worklog(issue_id_or_key, id, expand=expand)

Get worklog

Returns a worklog.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  If the worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
id = 'id_example' # str | The ID of the worklog.
expand = '' # str | Use [expand](#expansion) to include additional information about work logs in the response. This parameter accepts  `properties`, which returns worklog properties. (optional)

try:
    # Get worklog
    api_response = api_instance.get_worklog(issue_id_or_key, id, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->get_worklog: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **id** | **str**| The ID of the worklog. | 
 **expand** | **str**| Use [expand](#expansion) to include additional information about work logs in the response. This parameter accepts  &#x60;properties&#x60;, which returns worklog properties. | [optional] 

### Return type

[**Worklog**](Worklog.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_worklogs_for_ids**
> list[Worklog] get_worklogs_for_ids(body, expand=expand)

Get worklogs

Returns worklog details for a list of worklog IDs.  The returned list of worklogs is limited to 1000 items.  **[Permissions](#permissions) required:** Permission to access Jira, however, worklogs are only returned where either of the following is true:   *  the worklog is set as *Viewable by All Users*.  *  the user is a member of a project role or group with permission to view the worklog.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
body = jira_client.WorklogIdsRequestBean() # WorklogIdsRequestBean | A JSON object containing a list of worklog IDs.
expand = '' # str | Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts `properties` that returns the properties of each worklog. (optional)

try:
    # Get worklogs
    api_response = api_instance.get_worklogs_for_ids(body, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->get_worklogs_for_ids: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorklogIdsRequestBean**](WorklogIdsRequestBean.md)| A JSON object containing a list of worklog IDs. | 
 **expand** | **str**| Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts &#x60;properties&#x60; that returns the properties of each worklog. | [optional] 

### Return type

[**list[Worklog]**](Worklog.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_worklog**
> Worklog update_worklog(body, issue_id_or_key, id, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, expand=expand, override_editable_flag=override_editable_flag)

Update worklog

Updates a worklog.  Time tracking must be enabled in Jira, otherwise this operation returns an error. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  *  *Edit all worklogs*[ project permission](https://confluence.atlassian.com/x/yodKLg) to update any worklog or *Edit own worklogs* to update worklogs created by the user.  *  If the worklog has visibility restrictions, belongs to the group or has the role visibility is restricted to.

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
api_instance = jira_client.IssueWorklogsApi(jira_client.ApiClient(configuration))
body = {
  "comment" : {
    "content" : [ {
      "content" : [ {
        "text" : "I did some work here.",
        "type" : "text"
      } ],
      "type" : "paragraph"
    } ],
    "type" : "doc",
    "version" : 1
  },
  "started" : "2021-01-17T12:34:00.000+0000",
  "timeSpentSeconds" : 12000,
  "visibility" : {
    "identifier" : "276f955c-63d7-42c8-9520-92d01dca0625",
    "type" : "group"
  }
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key the issue.
id = 'id_example' # str | The ID of the worklog.
notify_users = true # bool | Whether users watching the issue are notified by email. (optional) (default to true)
adjust_estimate = 'auto' # str | Defines how to update the issue's time estimate, the options are:   *  `new` Sets the estimate to a specific value, defined in `newEstimate`.  *  `leave` Leaves the estimate unchanged.  *  `auto` Updates the estimate by the difference between the original and updated value of `timeSpent` or `timeSpentSeconds`. (optional) (default to auto)
new_estimate = 'new_estimate_example' # str | The value to set as the issue's remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when `adjustEstimate` is `new`. (optional)
expand = '' # str | Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts `properties`, which returns worklog properties. (optional)
override_editable_flag = false # bool | Whether the worklog should be added to the issue even if the issue is not editable. For example, because the issue is closed. Connect and Forge app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) can use this flag. (optional) (default to false)

try:
    # Update worklog
    api_response = api_instance.update_worklog(body, issue_id_or_key, id, notify_users=notify_users, adjust_estimate=adjust_estimate, new_estimate=new_estimate, expand=expand, override_editable_flag=override_editable_flag)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueWorklogsApi->update_worklog: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key the issue. | 
 **id** | **str**| The ID of the worklog. | 
 **notify_users** | **bool**| Whether users watching the issue are notified by email. | [optional] [default to true]
 **adjust_estimate** | **str**| Defines how to update the issue&#x27;s time estimate, the options are:   *  &#x60;new&#x60; Sets the estimate to a specific value, defined in &#x60;newEstimate&#x60;.  *  &#x60;leave&#x60; Leaves the estimate unchanged.  *  &#x60;auto&#x60; Updates the estimate by the difference between the original and updated value of &#x60;timeSpent&#x60; or &#x60;timeSpentSeconds&#x60;. | [optional] [default to auto]
 **new_estimate** | **str**| The value to set as the issue&#x27;s remaining time estimate, as days (\\#d), hours (\\#h), or minutes (\\#m or \\#). For example, *2d*. Required when &#x60;adjustEstimate&#x60; is &#x60;new&#x60;. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about worklogs in the response. This parameter accepts &#x60;properties&#x60;, which returns worklog properties. | [optional] 
 **override_editable_flag** | **bool**| Whether the worklog should be added to the issue even if the issue is not editable. For example, because the issue is closed. Connect and Forge app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) can use this flag. | [optional] [default to false]

### Return type

[**Worklog**](Worklog.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

