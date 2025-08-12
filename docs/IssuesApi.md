# jira_client.IssuesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**archive_issues**](IssuesApi.md#archive_issues) | **PUT** /rest/api/3/issue/archive | Archive issue(s) by issue ID/key
[**archive_issues_async**](IssuesApi.md#archive_issues_async) | **POST** /rest/api/3/issue/archive | Archive issue(s) by JQL
[**assign_issue**](IssuesApi.md#assign_issue) | **PUT** /rest/api/3/issue/{issueIdOrKey}/assignee | Assign issue
[**bulk_fetch_issues**](IssuesApi.md#bulk_fetch_issues) | **POST** /rest/api/3/issue/bulkfetch | Bulk fetch issues
[**create_issue**](IssuesApi.md#create_issue) | **POST** /rest/api/3/issue | Create issue
[**create_issues**](IssuesApi.md#create_issues) | **POST** /rest/api/3/issue/bulk | Bulk create issue
[**delete_issue**](IssuesApi.md#delete_issue) | **DELETE** /rest/api/3/issue/{issueIdOrKey} | Delete issue
[**do_transition**](IssuesApi.md#do_transition) | **POST** /rest/api/3/issue/{issueIdOrKey}/transitions | Transition issue
[**edit_issue**](IssuesApi.md#edit_issue) | **PUT** /rest/api/3/issue/{issueIdOrKey} | Edit issue
[**export_archived_issues**](IssuesApi.md#export_archived_issues) | **PUT** /rest/api/3/issues/archive/export | Export archived issue(s)
[**get_bulk_changelogs**](IssuesApi.md#get_bulk_changelogs) | **POST** /rest/api/3/changelog/bulkfetch | Bulk fetch changelogs
[**get_change_logs**](IssuesApi.md#get_change_logs) | **GET** /rest/api/3/issue/{issueIdOrKey}/changelog | Get changelogs
[**get_change_logs_by_ids**](IssuesApi.md#get_change_logs_by_ids) | **POST** /rest/api/3/issue/{issueIdOrKey}/changelog/list | Get changelogs by IDs
[**get_create_issue_meta**](IssuesApi.md#get_create_issue_meta) | **GET** /rest/api/3/issue/createmeta | Get create issue metadata
[**get_create_issue_meta_issue_type_id**](IssuesApi.md#get_create_issue_meta_issue_type_id) | **GET** /rest/api/3/issue/createmeta/{projectIdOrKey}/issuetypes/{issueTypeId} | Get create field metadata for a project and issue type id
[**get_create_issue_meta_issue_types**](IssuesApi.md#get_create_issue_meta_issue_types) | **GET** /rest/api/3/issue/createmeta/{projectIdOrKey}/issuetypes | Get create metadata issue types for a project
[**get_edit_issue_meta**](IssuesApi.md#get_edit_issue_meta) | **GET** /rest/api/3/issue/{issueIdOrKey}/editmeta | Get edit issue metadata
[**get_events**](IssuesApi.md#get_events) | **GET** /rest/api/3/events | Get events
[**get_issue**](IssuesApi.md#get_issue) | **GET** /rest/api/3/issue/{issueIdOrKey} | Get issue
[**get_issue_limit_report**](IssuesApi.md#get_issue_limit_report) | **GET** /rest/api/3/issue/limit/report | Get issue limit report
[**get_transitions**](IssuesApi.md#get_transitions) | **GET** /rest/api/3/issue/{issueIdOrKey}/transitions | Get transitions
[**notify**](IssuesApi.md#notify) | **POST** /rest/api/3/issue/{issueIdOrKey}/notify | Send notification for issue
[**unarchive_issues**](IssuesApi.md#unarchive_issues) | **PUT** /rest/api/3/issue/unarchive | Unarchive issue(s) by issue keys/ID

# **archive_issues**
> IssueArchivalSyncResponse archive_issues(body)

Archive issue(s) by issue ID/key

Enables admins to archive up to 1000 issues in a single request using issue ID/key, returning details of the issue(s) archived in the process and the errors encountered, if any.  **Note that:**   *  you can't archive subtasks directly, only through their parent issues  *  you can only archive issues from software, service management, and business projects  **[Permissions](#permissions) required:** Jira admin or site admin: [global permission](https://confluence.atlassian.com/x/x4dKLg)  **License required:** Premium or Enterprise  **Signed-in users only:** This API can't be accessed anonymously.     

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueArchivalSyncRequest() # IssueArchivalSyncRequest | Contains a list of issue keys or IDs to be archived.

try:
    # Archive issue(s) by issue ID/key
    api_response = api_instance.archive_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->archive_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueArchivalSyncRequest**](IssueArchivalSyncRequest.md)| Contains a list of issue keys or IDs to be archived. | 

### Return type

[**IssueArchivalSyncResponse**](IssueArchivalSyncResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **archive_issues_async**
> str archive_issues_async(body)

Archive issue(s) by JQL

Enables admins to archive up to 100,000 issues in a single request using JQL, returning the URL to check the status of the submitted request.  You can use the [get task](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-tasks/#api-rest-api-3-task-taskid-get) and [cancel task](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-tasks/#api-rest-api-3-task-taskid-cancel-post) APIs to manage the request.  **Note that:**   *  you can't archive subtasks directly, only through their parent issues  *  you can only archive issues from software, service management, and business projects  **[Permissions](#permissions) required:** Jira admin or site admin: [global permission](https://confluence.atlassian.com/x/x4dKLg)  **License required:** Premium or Enterprise  **Signed-in users only:** This API can't be accessed anonymously.  **Rate limiting:** Only a single request per jira instance can be active at any given time.     

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.ArchiveIssueAsyncRequest() # ArchiveIssueAsyncRequest | A JQL query specifying the issues to archive. Note that subtasks can only be archived through their parent issues.

try:
    # Archive issue(s) by JQL
    api_response = api_instance.archive_issues_async(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->archive_issues_async: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ArchiveIssueAsyncRequest**](ArchiveIssueAsyncRequest.md)| A JQL query specifying the issues to archive. Note that subtasks can only be archived through their parent issues. | 

### Return type

**str**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **assign_issue**
> object assign_issue(body, issue_id_or_key)

Assign issue

Assigns an issue to a user. Use this operation when the calling user does not have the *Edit Issues* permission but has the *Assign issue* permission for the project that the issue is in.  If `name` or `accountId` is set to:   *  `\"-1\"`, the issue is assigned to the default assignee for the project.  *  `null`, the issue is set to unassigned.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse Projects* and *Assign Issues* [ project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.User() # User | The request object with the user that the issue is assigned to.
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue to be assigned.

try:
    # Assign issue
    api_response = api_instance.assign_issue(body, issue_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->assign_issue: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**User**](User.md)| The request object with the user that the issue is assigned to. | 
 **issue_id_or_key** | **str**| The ID or key of the issue to be assigned. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulk_fetch_issues**
> BulkIssueResults bulk_fetch_issues(body)

Bulk fetch issues

Returns the details for a set of requested issues. You can request up to 100 issues.  Each issue is identified by its ID or key, however, if the identifier doesn't match an issue, a case-insensitive search and check for moved issues is performed. If a matching issue is found its details are returned, a 302 or other redirect is **not** returned.  Issues will be returned in ascending `id` order. If there are errors, Jira will return a list of issues which couldn't be fetched along with error messages.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.BulkFetchIssueRequestBean() # BulkFetchIssueRequestBean | A JSON object containing the information about which issues and fields to fetch.

try:
    # Bulk fetch issues
    api_response = api_instance.bulk_fetch_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->bulk_fetch_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkFetchIssueRequestBean**](BulkFetchIssueRequestBean.md)| A JSON object containing the information about which issues and fields to fetch. | 

### Return type

[**BulkIssueResults**](BulkIssueResults.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issue**
> CreatedIssue create_issue(body, update_history=update_history)

Create issue

Creates an issue or, where the option to create subtasks is enabled in Jira, a subtask. A transition may be applied, to move the issue or subtask to a workflow step other than the default start step, and issue properties set.  The content of the issue or subtask is defined using `update` and `fields`. The fields that can be set in the issue or subtask are determined using the [ Get create issue metadata](#api-rest-api-3-issue-createmeta-get). These are the same fields that appear on the issue's create screen. Note that the `description`, `environment`, and any `textarea` type custom fields (multi-line text fields) take Atlassian Document Format content. Single line custom fields (`textfield`) accept a string and don't handle Atlassian Document Format content.  Creating a subtask differs from creating an issue as follows:   *  `issueType` must be set to a subtask issue type (use [ Get create issue metadata](#api-rest-api-3-issue-createmeta-get) to find subtask issue types).  *  `parent` must contain the ID or key of the parent issue.  In a next-gen project any issue may be made a child providing that the parent and child are members of the same project.  **[Permissions](#permissions) required:** *Browse projects* and *Create issues* [project permissions](https://confluence.atlassian.com/x/yodKLg) for the project in which the issue or subtask is created.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "fields" : {
    "assignee" : {
      "id" : "5b109f2e9729b51b54dc274d"
    },
    "components" : [ {
      "id" : "10000"
    } ],
    "customfield_10000" : "09/Jun/19",
    "customfield_20000" : "06/Jul/19 3:25 PM",
    "customfield_30000" : [ "10000", "10002" ],
    "customfield_40000" : {
      "content" : [ {
        "content" : [ {
          "text" : "Occurs on all orders",
          "type" : "text"
        } ],
        "type" : "paragraph"
      } ],
      "type" : "doc",
      "version" : 1
    },
    "customfield_50000" : {
      "content" : [ {
        "content" : [ {
          "text" : "Could impact day-to-day work.",
          "type" : "text"
        } ],
        "type" : "paragraph"
      } ],
      "type" : "doc",
      "version" : 1
    },
    "customfield_60000" : "jira-software-users",
    "customfield_70000" : [ "jira-administrators", "jira-software-users" ],
    "customfield_80000" : {
      "value" : "red"
    },
    "description" : {
      "content" : [ {
        "content" : [ {
          "text" : "Order entry fails when selecting supplier.",
          "type" : "text"
        } ],
        "type" : "paragraph"
      } ],
      "type" : "doc",
      "version" : 1
    },
    "duedate" : "2019-05-11",
    "environment" : {
      "content" : [ {
        "content" : [ {
          "text" : "UAT",
          "type" : "text"
        } ],
        "type" : "paragraph"
      } ],
      "type" : "doc",
      "version" : 1
    },
    "fixVersions" : [ {
      "id" : "10001"
    } ],
    "issuetype" : {
      "id" : "10000"
    },
    "labels" : [ "bugfix", "blitz_test" ],
    "parent" : {
      "key" : "PROJ-123"
    },
    "priority" : {
      "id" : "20000"
    },
    "project" : {
      "id" : "10000"
    },
    "reporter" : {
      "id" : "5b10a2844c20165700ede21g"
    },
    "security" : {
      "id" : "10000"
    },
    "summary" : "Main order flow broken",
    "timetracking" : {
      "originalEstimate" : "10",
      "remainingEstimate" : "5"
    },
    "versions" : [ {
      "id" : "10000"
    } ]
  },
  "update" : { }
} # dict(str, object) | 
update_history = false # bool | Whether the project in which the issue is created is added to the user's **Recently viewed** project list, as shown under **Projects** in Jira. When provided, the issue type and request type are added to the user's history for a project. These values are then used to provide defaults on the issue create screen. (optional) (default to false)

try:
    # Create issue
    api_response = api_instance.create_issue(body, update_history=update_history)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->create_issue: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **update_history** | **bool**| Whether the project in which the issue is created is added to the user&#x27;s **Recently viewed** project list, as shown under **Projects** in Jira. When provided, the issue type and request type are added to the user&#x27;s history for a project. These values are then used to provide defaults on the issue create screen. | [optional] [default to false]

### Return type

[**CreatedIssue**](CreatedIssue.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issues**
> CreatedIssues create_issues(body)

Bulk create issue

Creates upto **50** issues and, where the option to create subtasks is enabled in Jira, subtasks. Transitions may be applied, to move the issues or subtasks to a workflow step other than the default start step, and issue properties set.  The content of each issue or subtask is defined using `update` and `fields`. The fields that can be set in the issue or subtask are determined using the [ Get create issue metadata](#api-rest-api-3-issue-createmeta-get). These are the same fields that appear on the issues' create screens. Note that the `description`, `environment`, and any `textarea` type custom fields (multi-line text fields) take Atlassian Document Format content. Single line custom fields (`textfield`) accept a string and don't handle Atlassian Document Format content.  Creating a subtask differs from creating an issue as follows:   *  `issueType` must be set to a subtask issue type (use [ Get create issue metadata](#api-rest-api-3-issue-createmeta-get) to find subtask issue types).  *  `parent` the must contain the ID or key of the parent issue.  **[Permissions](#permissions) required:** *Browse projects* and *Create issues* [project permissions](https://confluence.atlassian.com/x/yodKLg) for the project in which each issue or subtask is created.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "issueUpdates" : [ {
    "fields" : {
      "assignee" : {
        "id" : "5b109f2e9729b51b54dc274d"
      },
      "components" : [ {
        "id" : "10000"
      } ],
      "customfield_10000" : "09/Jun/19",
      "customfield_20000" : "06/Jul/19 3:25 PM",
      "customfield_30000" : [ "10000", "10002" ],
      "customfield_40000" : {
        "content" : [ {
          "content" : [ {
            "text" : "Occurs on all orders",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "customfield_50000" : {
        "content" : [ {
          "content" : [ {
            "text" : "Could impact day-to-day work.",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "customfield_60000" : "jira-software-users",
      "customfield_70000" : [ "jira-administrators", "jira-software-users" ],
      "customfield_80000" : {
        "value" : "red"
      },
      "description" : {
        "content" : [ {
          "content" : [ {
            "text" : "Order entry fails when selecting supplier.",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "duedate" : "2011-03-11",
      "environment" : {
        "content" : [ {
          "content" : [ {
            "text" : "UAT",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "fixVersions" : [ {
        "id" : "10001"
      } ],
      "issuetype" : {
        "id" : "10000"
      },
      "labels" : [ "bugfix", "blitz_test" ],
      "priority" : {
        "id" : "20000"
      },
      "project" : {
        "id" : "10000"
      },
      "reporter" : {
        "id" : "5b10a2844c20165700ede21g"
      },
      "security" : {
        "id" : "10000"
      },
      "summary" : "Main order flow broken",
      "timetracking" : {
        "originalEstimate" : "10",
        "remainingEstimate" : "5"
      },
      "versions" : [ {
        "id" : "10000"
      } ]
    },
    "update" : {
      "worklog" : [ {
        "add" : {
          "started" : "2019-07-05T11:05:00.000+0000",
          "timeSpent" : "60m"
        }
      } ]
    }
  }, {
    "fields" : {
      "assignee" : {
        "id" : "5b109f2e9729b51b54dc274d"
      },
      "components" : [ {
        "id" : "10000"
      } ],
      "customfield_10000" : "09/Jun/19",
      "customfield_20000" : "06/Jul/19 3:25 PM",
      "customfield_30000" : [ "10000", "10002" ],
      "customfield_40000" : {
        "content" : [ {
          "content" : [ {
            "text" : "Occurs on all orders",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "customfield_50000" : {
        "content" : [ {
          "content" : [ {
            "text" : "Could impact day-to-day work.",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "customfield_60000" : "jira-software-users",
      "customfield_70000" : [ "jira-administrators", "jira-software-users" ],
      "customfield_80000" : {
        "value" : "red"
      },
      "description" : {
        "content" : [ {
          "content" : [ {
            "text" : "Order remains pending after approved.",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "duedate" : "2019-04-16",
      "environment" : {
        "content" : [ {
          "content" : [ {
            "text" : "UAT",
            "type" : "text"
          } ],
          "type" : "paragraph"
        } ],
        "type" : "doc",
        "version" : 1
      },
      "fixVersions" : [ {
        "id" : "10001"
      } ],
      "issuetype" : {
        "id" : "10000"
      },
      "labels" : [ "new_release" ],
      "priority" : {
        "id" : "20000"
      },
      "project" : {
        "id" : "1000"
      },
      "reporter" : {
        "id" : "5b10a2844c20165700ede21g"
      },
      "security" : {
        "id" : "10000"
      },
      "summary" : "Order stuck in pending",
      "timetracking" : {
        "originalEstimate" : "15",
        "remainingEstimate" : "5"
      },
      "versions" : [ {
        "id" : "10000"
      } ]
    },
    "update" : { }
  } ]
} # dict(str, object) | 

try:
    # Bulk create issue
    api_response = api_instance.create_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->create_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

[**CreatedIssues**](CreatedIssues.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_issue**
> delete_issue(issue_id_or_key, delete_subtasks=delete_subtasks)

Delete issue

Deletes an issue.  An issue cannot be deleted if it has one or more subtasks. To delete an issue with subtasks, set `deleteSubtasks`. This causes the issue's subtasks to be deleted with the issue.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Delete issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
delete_subtasks = 'false' # str | Whether the issue's subtasks are deleted when the issue is deleted. (optional) (default to false)

try:
    # Delete issue
    api_instance.delete_issue(issue_id_or_key, delete_subtasks=delete_subtasks)
except ApiException as e:
    print("Exception when calling IssuesApi->delete_issue: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **delete_subtasks** | **str**| Whether the issue&#x27;s subtasks are deleted when the issue is deleted. | [optional] [default to false]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **do_transition**
> object do_transition(body, issue_id_or_key)

Transition issue

Performs an issue transition and, if the transition has a screen, updates the fields from the transition screen.  sortByCategory To update the fields on the transition screen, specify the fields in the `fields` or `update` parameters in the request body. Get details about the fields using [ Get transitions](#api-rest-api-3-issue-issueIdOrKey-transitions-get) with the `transitions.fields` expand.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Transition issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "fields" : {
    "assignee" : {
      "name" : "bob"
    },
    "resolution" : {
      "name" : "Fixed"
    }
  },
  "historyMetadata" : {
    "activityDescription" : "Complete order processing",
    "actor" : {
      "avatarUrl" : "http://mysystem/avatar/tony.jpg",
      "displayName" : "Tony",
      "id" : "tony",
      "type" : "mysystem-user",
      "url" : "http://mysystem/users/tony"
    },
    "cause" : {
      "id" : "myevent",
      "type" : "mysystem-event"
    },
    "description" : "From the order testing process",
    "extraData" : {
      "Iteration" : "10a",
      "Step" : "4"
    },
    "generator" : {
      "id" : "mysystem-1",
      "type" : "mysystem-application"
    },
    "type" : "myplugin:type"
  },
  "transition" : {
    "id" : "5"
  },
  "update" : {
    "comment" : [ {
      "add" : {
        "body" : {
          "content" : [ {
            "content" : [ {
              "text" : "Bug has been fixed",
              "type" : "text"
            } ],
            "type" : "paragraph"
          } ],
          "type" : "doc",
          "version" : 1
        }
      }
    } ]
  }
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.

try:
    # Transition issue
    api_response = api_instance.do_transition(body, issue_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->do_transition: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **edit_issue**
> object edit_issue(body, issue_id_or_key, notify_users=notify_users, override_screen_security=override_screen_security, override_editable_flag=override_editable_flag, return_issue=return_issue, expand=expand)

Edit issue

Edits an issue. Issue properties may be updated as part of the edit. Please note that issue transition is not supported and is ignored here. To transition an issue, please use [Transition issue](#api-rest-api-3-issue-issueIdOrKey-transitions-post).  The edits to the issue's fields are defined using `update` and `fields`. The fields that can be edited are determined using [ Get edit issue metadata](#api-rest-api-3-issue-issueIdOrKey-editmeta-get).  The parent field may be set by key or ID. For standard issue types, the parent may be removed by setting `update.parent.set.none` to *true*. Note that the `description`, `environment`, and any `textarea` type custom fields (multi-line text fields) take Atlassian Document Format content. Single line custom fields (`textfield`) accept a string and don't handle Atlassian Document Format content.  Connect apps having an app user with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), can override the screen security configuration using `overrideScreenSecurity` and `overrideEditableFlag`.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Edit issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "fields" : {
    "customfield_10000" : {
      "content" : [ {
        "content" : [ {
          "text" : "Investigation underway",
          "type" : "text"
        } ],
        "type" : "paragraph"
      } ],
      "type" : "doc",
      "version" : 1
    },
    "customfield_10010" : 1,
    "summary" : "Completed orders still displaying in pending"
  },
  "historyMetadata" : {
    "activityDescription" : "Complete order processing",
    "actor" : {
      "avatarUrl" : "http://mysystem/avatar/tony.jpg",
      "displayName" : "Tony",
      "id" : "tony",
      "type" : "mysystem-user",
      "url" : "http://mysystem/users/tony"
    },
    "cause" : {
      "id" : "myevent",
      "type" : "mysystem-event"
    },
    "description" : "From the order testing process",
    "extraData" : {
      "Iteration" : "10a",
      "Step" : "4"
    },
    "generator" : {
      "id" : "mysystem-1",
      "type" : "mysystem-application"
    },
    "type" : "myplugin:type"
  },
  "properties" : [ {
    "key" : "key1",
    "value" : "Order number 10784"
  }, {
    "key" : "key2",
    "value" : "Order number 10923"
  } ],
  "update" : {
    "components" : [ {
      "set" : ""
    } ],
    "labels" : [ {
      "add" : "triaged"
    }, {
      "remove" : "blocker"
    } ],
    "summary" : [ {
      "set" : "Bug in business logic"
    } ],
    "timetracking" : [ {
      "edit" : {
        "originalEstimate" : "1w 1d",
        "remainingEstimate" : "4d"
      }
    } ]
  }
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
notify_users = true # bool | Whether a notification email about the issue update is sent to all watchers. To disable the notification, administer Jira or administer project permissions are required. If the user doesn't have the necessary permission the request is ignored. (optional) (default to true)
override_screen_security = false # bool | Whether screen security is overridden to enable hidden fields to be edited. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). (optional) (default to false)
override_editable_flag = false # bool | Whether screen security is overridden to enable uneditable fields to be edited. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). (optional) (default to false)
return_issue = false # bool | Whether the response should contain the issue with fields edited in this request. The returned issue will have the same format as in the [Get issue API](#api-rest-api-3-issue-issueidorkey-get). (optional) (default to false)
expand = '' # str | The Get issue API expand parameter to use in the response if the `returnIssue` parameter is `true`. (optional)

try:
    # Edit issue
    api_response = api_instance.edit_issue(body, issue_id_or_key, notify_users=notify_users, override_screen_security=override_screen_security, override_editable_flag=override_editable_flag, return_issue=return_issue, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->edit_issue: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **notify_users** | **bool**| Whether a notification email about the issue update is sent to all watchers. To disable the notification, administer Jira or administer project permissions are required. If the user doesn&#x27;t have the necessary permission the request is ignored. | [optional] [default to true]
 **override_screen_security** | **bool**| Whether screen security is overridden to enable hidden fields to be edited. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). | [optional] [default to false]
 **override_editable_flag** | **bool**| Whether screen security is overridden to enable uneditable fields to be edited. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). | [optional] [default to false]
 **return_issue** | **bool**| Whether the response should contain the issue with fields edited in this request. The returned issue will have the same format as in the [Get issue API](#api-rest-api-3-issue-issueidorkey-get). | [optional] [default to false]
 **expand** | **str**| The Get issue API expand parameter to use in the response if the &#x60;returnIssue&#x60; parameter is &#x60;true&#x60;. | [optional] 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **export_archived_issues**
> ExportArchivedIssuesTaskProgressResponse export_archived_issues(body)

Export archived issue(s)

Enables admins to retrieve details of all archived issues. Upon a successful request, the admin who submitted it will receive an email with a link to download a CSV file with the issue details.  Note that this API only exports the values of system fields and archival-specific fields (`ArchivedBy` and `ArchivedDate`). Custom fields aren't supported.  **[Permissions](#permissions) required:** Jira admin or site admin: [global permission](https://confluence.atlassian.com/x/x4dKLg)  **License required:** Premium or Enterprise  **Signed-in users only:** This API can't be accessed anonymously.  **Rate limiting:** Only a single request can be active at any given time.     

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "archivedBy" : [ "uuid-rep-001", "uuid-rep-002" ],
  "archivedDate" : {
    "dateAfter" : "2023-01-01",
    "dateBefore" : "2023-01-12"
  },
  "archivedDateRange" : {
    "dateAfter" : "2023-01-01",
    "dateBefore" : "2023-01-12"
  },
  "issueTypes" : [ "10001", "10002" ],
  "projects" : [ "FOO", "BAR" ],
  "reporters" : [ "uuid-rep-001", "uuid-rep-002" ]
} # dict(str, object) | You can filter the issues in your request by the `projects`, `archivedBy`, `archivedDate`, `issueTypes`, and `reporters` fields. All filters are optional. If you don't provide any filters, you'll get a list of up to one million archived issues.

try:
    # Export archived issue(s)
    api_response = api_instance.export_archived_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->export_archived_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)| You can filter the issues in your request by the &#x60;projects&#x60;, &#x60;archivedBy&#x60;, &#x60;archivedDate&#x60;, &#x60;issueTypes&#x60;, and &#x60;reporters&#x60; fields. All filters are optional. If you don&#x27;t provide any filters, you&#x27;ll get a list of up to one million archived issues. | 

### Return type

[**ExportArchivedIssuesTaskProgressResponse**](ExportArchivedIssuesTaskProgressResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_bulk_changelogs**
> BulkChangelogResponseBean get_bulk_changelogs(body)

Bulk fetch changelogs

Bulk fetch changelogs for multiple issues and filter by fields  Returns a paginated list of all changelogs for given issues sorted by changelog date and issue IDs, starting from the oldest changelog and smallest issue ID.  Issues are identified by their ID or key, and optionally changelogs can be filtered by their field IDs. You can request the changelogs of up to 1000 issues and can filter them by up to 10 field IDs.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the projects that the issues are in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issues.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.BulkChangelogRequestBean() # BulkChangelogRequestBean | A JSON object containing the bulk fetch changelog request filters such as issue IDs and field IDs.

try:
    # Bulk fetch changelogs
    api_response = api_instance.get_bulk_changelogs(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_bulk_changelogs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkChangelogRequestBean**](BulkChangelogRequestBean.md)| A JSON object containing the bulk fetch changelog request filters such as issue IDs and field IDs. | 

### Return type

[**BulkChangelogResponseBean**](BulkChangelogResponseBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_change_logs**
> PageBeanChangelog get_change_logs(issue_id_or_key, start_at=start_at, max_results=max_results)

Get changelogs

Returns a [paginated](#pagination) list of all changelogs for an issue sorted by date, starting from the oldest.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)

try:
    # Get changelogs
    api_response = api_instance.get_change_logs(issue_id_or_key, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_change_logs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]

### Return type

[**PageBeanChangelog**](PageBeanChangelog.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_change_logs_by_ids**
> PageOfChangelogs get_change_logs_by_ids(body, issue_id_or_key)

Get changelogs by IDs

Returns changelogs for an issue specified by a list of changelog IDs.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueChangelogIds() # IssueChangelogIds | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.

try:
    # Get changelogs by IDs
    api_response = api_instance.get_change_logs_by_ids(body, issue_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_change_logs_by_ids: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueChangelogIds**](IssueChangelogIds.md)|  | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 

### Return type

[**PageOfChangelogs**](PageOfChangelogs.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_create_issue_meta**
> IssueCreateMetadata get_create_issue_meta(project_ids=project_ids, project_keys=project_keys, issuetype_ids=issuetype_ids, issuetype_names=issuetype_names, expand=expand)

Get create issue metadata

Returns details of projects, issue types within projects, and, when requested, the create screen fields for each issue type for the user. Use the information to populate the requests in [ Create issue](#api-rest-api-3-issue-post) and [Create issues](#api-rest-api-3-issue-bulk-post).  Deprecated, see [Create Issue Meta Endpoint Deprecation Notice](https://developer.atlassian.com/cloud/jira/platform/changelog/#CHANGE-1304).  The request can be restricted to specific projects or issue types using the query parameters. The response will contain information for the valid projects, issue types, or project and issue type combinations requested. Note that invalid project, issue type, or project and issue type combinations do not generate errors.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Create issues* [project permission](https://confluence.atlassian.com/x/yodKLg) in the requested projects.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
project_ids = ['project_ids_example'] # list[str] | List of project IDs. This parameter accepts a comma-separated list. Multiple project IDs can also be provided using an ampersand-separated list. For example, `projectIds=10000,10001&projectIds=10020,10021`. This parameter may be provided with `projectKeys`. (optional)
project_keys = ['project_keys_example'] # list[str] | List of project keys. This parameter accepts a comma-separated list. Multiple project keys can also be provided using an ampersand-separated list. For example, `projectKeys=proj1,proj2&projectKeys=proj3`. This parameter may be provided with `projectIds`. (optional)
issuetype_ids = ['issuetype_ids_example'] # list[str] | List of issue type IDs. This parameter accepts a comma-separated list. Multiple issue type IDs can also be provided using an ampersand-separated list. For example, `issuetypeIds=10000,10001&issuetypeIds=10020,10021`. This parameter may be provided with `issuetypeNames`. (optional)
issuetype_names = ['issuetype_names_example'] # list[str] | List of issue type names. This parameter accepts a comma-separated list. Multiple issue type names can also be provided using an ampersand-separated list. For example, `issuetypeNames=name1,name2&issuetypeNames=name3`. This parameter may be provided with `issuetypeIds`. (optional)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about issue metadata in the response. This parameter accepts `projects.issuetypes.fields`, which returns information about the fields in the issue creation screen for each issue type. Fields hidden from the screen are not returned. Use the information to populate the `fields` and `update` fields in [Create issue](#api-rest-api-3-issue-post) and [Create issues](#api-rest-api-3-issue-bulk-post). (optional)

try:
    # Get create issue metadata
    api_response = api_instance.get_create_issue_meta(project_ids=project_ids, project_keys=project_keys, issuetype_ids=issuetype_ids, issuetype_names=issuetype_names, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_create_issue_meta: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_ids** | [**list[str]**](str.md)| List of project IDs. This parameter accepts a comma-separated list. Multiple project IDs can also be provided using an ampersand-separated list. For example, &#x60;projectIds&#x3D;10000,10001&amp;projectIds&#x3D;10020,10021&#x60;. This parameter may be provided with &#x60;projectKeys&#x60;. | [optional] 
 **project_keys** | [**list[str]**](str.md)| List of project keys. This parameter accepts a comma-separated list. Multiple project keys can also be provided using an ampersand-separated list. For example, &#x60;projectKeys&#x3D;proj1,proj2&amp;projectKeys&#x3D;proj3&#x60;. This parameter may be provided with &#x60;projectIds&#x60;. | [optional] 
 **issuetype_ids** | [**list[str]**](str.md)| List of issue type IDs. This parameter accepts a comma-separated list. Multiple issue type IDs can also be provided using an ampersand-separated list. For example, &#x60;issuetypeIds&#x3D;10000,10001&amp;issuetypeIds&#x3D;10020,10021&#x60;. This parameter may be provided with &#x60;issuetypeNames&#x60;. | [optional] 
 **issuetype_names** | [**list[str]**](str.md)| List of issue type names. This parameter accepts a comma-separated list. Multiple issue type names can also be provided using an ampersand-separated list. For example, &#x60;issuetypeNames&#x3D;name1,name2&amp;issuetypeNames&#x3D;name3&#x60;. This parameter may be provided with &#x60;issuetypeIds&#x60;. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about issue metadata in the response. This parameter accepts &#x60;projects.issuetypes.fields&#x60;, which returns information about the fields in the issue creation screen for each issue type. Fields hidden from the screen are not returned. Use the information to populate the &#x60;fields&#x60; and &#x60;update&#x60; fields in [Create issue](#api-rest-api-3-issue-post) and [Create issues](#api-rest-api-3-issue-bulk-post). | [optional] 

### Return type

[**IssueCreateMetadata**](IssueCreateMetadata.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_create_issue_meta_issue_type_id**
> PageOfCreateMetaIssueTypeWithField get_create_issue_meta_issue_type_id(project_id_or_key, issue_type_id, start_at=start_at, max_results=max_results)

Get create field metadata for a project and issue type id

Returns a page of field metadata for a specified project and issuetype id. Use the information to populate the requests in [ Create issue](#api-rest-api-3-issue-post) and [Create issues](#api-rest-api-3-issue-bulk-post).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Create issues* [project permission](https://confluence.atlassian.com/x/yodKLg) in the requested projects.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The ID or key of the project.
issue_type_id = 'issue_type_id_example' # str | The issuetype ID.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get create field metadata for a project and issue type id
    api_response = api_instance.get_create_issue_meta_issue_type_id(project_id_or_key, issue_type_id, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_create_issue_meta_issue_type_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The ID or key of the project. | 
 **issue_type_id** | **str**| The issuetype ID. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageOfCreateMetaIssueTypeWithField**](PageOfCreateMetaIssueTypeWithField.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_create_issue_meta_issue_types**
> PageOfCreateMetaIssueTypes get_create_issue_meta_issue_types(project_id_or_key, start_at=start_at, max_results=max_results)

Get create metadata issue types for a project

Returns a page of issue type metadata for a specified project. Use the information to populate the requests in [ Create issue](#api-rest-api-3-issue-post) and [Create issues](#api-rest-api-3-issue-bulk-post).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Create issues* [project permission](https://confluence.atlassian.com/x/yodKLg) in the requested projects.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The ID or key of the project.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)

try:
    # Get create metadata issue types for a project
    api_response = api_instance.get_create_issue_meta_issue_types(project_id_or_key, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_create_issue_meta_issue_types: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The ID or key of the project. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]

### Return type

[**PageOfCreateMetaIssueTypes**](PageOfCreateMetaIssueTypes.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_edit_issue_meta**
> IssueUpdateMetadata get_edit_issue_meta(issue_id_or_key, override_screen_security=override_screen_security, override_editable_flag=override_editable_flag)

Get edit issue metadata

Returns the edit screen fields for an issue that are visible to and editable by the user. Use the information to populate the requests in [Edit issue](#api-rest-api-3-issue-issueIdOrKey-put).  This endpoint will check for these conditions:  1.  Field is available on a field screen - through screen, screen scheme, issue type screen scheme, and issue type scheme configuration. `overrideScreenSecurity=true` skips this condition. 2.  Field is visible in the [field configuration](https://support.atlassian.com/jira-cloud-administration/docs/change-a-field-configuration/). `overrideScreenSecurity=true` skips this condition. 3.  Field is shown on the issue: each field has different conditions here. For example: Attachment field only shows if attachments are enabled. Assignee only shows if user has permissions to assign the issue. 4.  If a field is custom then it must have valid custom field context, applicable for its project and issue type. All system fields are assumed to have context in all projects and all issue types. 5.  Issue has a project, issue type, and status defined. 6.  Issue is assigned to a valid workflow, and the current status has assigned a workflow step. `overrideEditableFlag=true` skips this condition. 7.  The current workflow step is editable. This is true by default, but [can be disabled by setting](https://support.atlassian.com/jira-cloud-administration/docs/use-workflow-properties/) the `jira.issue.editable` property to `false`. `overrideEditableFlag=true` skips this condition. 8.  User has [Edit issues permission](https://support.atlassian.com/jira-cloud-administration/docs/permissions-for-company-managed-projects/). 9.  Workflow permissions allow editing a field. This is true by default but [can be modified](https://support.atlassian.com/jira-cloud-administration/docs/use-workflow-properties/) using `jira.permission.*` workflow properties.  Fields hidden using [Issue layout settings page](https://support.atlassian.com/jira-software-cloud/docs/configure-field-layout-in-the-issue-view/) remain editable.  Connect apps having an app user with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), can return additional details using:   *  `overrideScreenSecurity` When this flag is `true`, then this endpoint skips checking if fields are available through screens, and field configuration (conditions 1. and 2. from the list above).  *  `overrideEditableFlag` When this flag is `true`, then this endpoint skips checking if workflow is present and if the current step is editable (conditions 6. and 7. from the list above).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  Note: For any fields to be editable the user must have the *Edit issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
override_screen_security = false # bool | Whether hidden fields are returned. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). (optional) (default to false)
override_editable_flag = false # bool | Whether non-editable fields are returned. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). (optional) (default to false)

try:
    # Get edit issue metadata
    api_response = api_instance.get_edit_issue_meta(issue_id_or_key, override_screen_security=override_screen_security, override_editable_flag=override_editable_flag)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_edit_issue_meta: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **override_screen_security** | **bool**| Whether hidden fields are returned. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). | [optional] [default to false]
 **override_editable_flag** | **bool**| Whether non-editable fields are returned. Available to Connect app users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) and Forge apps acting on behalf of users with *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). | [optional] [default to false]

### Return type

[**IssueUpdateMetadata**](IssueUpdateMetadata.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_events**
> list[IssueEvent] get_events()

Get events

Returns all issue events.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))

try:
    # Get events
    api_response = api_instance.get_events()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_events: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[IssueEvent]**](IssueEvent.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue**
> IssueBean get_issue(issue_id_or_key, fields=fields, fields_by_keys=fields_by_keys, expand=expand, properties=properties, update_history=update_history, fail_fast=fail_fast)

Get issue

Returns the details for an issue.  The issue is identified by its ID or key, however, if the identifier doesn't match an issue, a case-insensitive search and check for moved issues is performed. If a matching issue is found its details are returned, a 302 or other redirect is **not** returned. The issue key returned in the response is the key of the issue found.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
fields = ['fields_example'] # list[str] | A list of fields to return for the issue. This parameter accepts a comma-separated list. Use it to retrieve a subset of fields. Allowed values:   *  `*all` Returns all fields.  *  `*navigable` Returns navigable fields.  *  Any issue field, prefixed with a minus to exclude.  Examples:   *  `summary,comment` Returns only the summary and comments fields.  *  `-description` Returns all (default) fields except description.  *  `*navigable,-comment` Returns all navigable fields except comment.  This parameter may be specified multiple times. For example, `fields=field1,field2& fields=field3`.  Note: All fields are returned by default. This differs from [Search for issues using JQL (GET)](#api-rest-api-3-search-get) and [Search for issues using JQL (POST)](#api-rest-api-3-search-post) where the default is all navigable fields. (optional)
fields_by_keys = false # bool | Whether fields in `fields` are referenced by keys rather than IDs. This parameter is useful where fields have been added by a connect app and a field's key may differ from its ID. (optional) (default to false)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about the issues in the response. This parameter accepts a comma-separated list. Expand options include:   *  `renderedFields` Returns field values rendered in HTML format.  *  `names` Returns the display name of each field.  *  `schema` Returns the schema describing a field type.  *  `transitions` Returns all possible transitions for the issue.  *  `editmeta` Returns information about how each field can be edited.  *  `changelog` Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  `versionedRepresentations` Returns a JSON array for each version of a field's value, with the highest number representing the most recent version. Note: When included in the request, the `fields` parameter is ignored. (optional)
properties = ['properties_example'] # list[str] | A list of issue properties to return for the issue. This parameter accepts a comma-separated list. Allowed values:   *  `*all` Returns all issue properties.  *  Any issue property key, prefixed with a minus to exclude.  Examples:   *  `*all` Returns all properties.  *  `*all,-prop1` Returns all properties except `prop1`.  *  `prop1,prop2` Returns `prop1` and `prop2` properties.  This parameter may be specified multiple times. For example, `properties=prop1,prop2& properties=prop3`. (optional)
update_history = false # bool | Whether the project in which the issue is created is added to the user's **Recently viewed** project list, as shown under **Projects** in Jira. This also populates the [JQL issues search](#api-rest-api-3-search-get) `lastViewed` field. (optional) (default to false)
fail_fast = false # bool | Whether to fail the request quickly in case of an error while loading fields for an issue. For `failFast=true`, if one field fails, the entire operation fails. For `failFast=false`, the operation will continue even if a field fails. It will return a valid response, but without values for the failed field(s). (optional) (default to false)

try:
    # Get issue
    api_response = api_instance.get_issue(issue_id_or_key, fields=fields, fields_by_keys=fields_by_keys, expand=expand, properties=properties, update_history=update_history, fail_fast=fail_fast)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_issue: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **fields** | [**list[str]**](str.md)| A list of fields to return for the issue. This parameter accepts a comma-separated list. Use it to retrieve a subset of fields. Allowed values:   *  &#x60;*all&#x60; Returns all fields.  *  &#x60;*navigable&#x60; Returns navigable fields.  *  Any issue field, prefixed with a minus to exclude.  Examples:   *  &#x60;summary,comment&#x60; Returns only the summary and comments fields.  *  &#x60;-description&#x60; Returns all (default) fields except description.  *  &#x60;*navigable,-comment&#x60; Returns all navigable fields except comment.  This parameter may be specified multiple times. For example, &#x60;fields&#x3D;field1,field2&amp; fields&#x3D;field3&#x60;.  Note: All fields are returned by default. This differs from [Search for issues using JQL (GET)](#api-rest-api-3-search-get) and [Search for issues using JQL (POST)](#api-rest-api-3-search-post) where the default is all navigable fields. | [optional] 
 **fields_by_keys** | **bool**| Whether fields in &#x60;fields&#x60; are referenced by keys rather than IDs. This parameter is useful where fields have been added by a connect app and a field&#x27;s key may differ from its ID. | [optional] [default to false]
 **expand** | **str**| Use [expand](#expansion) to include additional information about the issues in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;renderedFields&#x60; Returns field values rendered in HTML format.  *  &#x60;names&#x60; Returns the display name of each field.  *  &#x60;schema&#x60; Returns the schema describing a field type.  *  &#x60;transitions&#x60; Returns all possible transitions for the issue.  *  &#x60;editmeta&#x60; Returns information about how each field can be edited.  *  &#x60;changelog&#x60; Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  &#x60;versionedRepresentations&#x60; Returns a JSON array for each version of a field&#x27;s value, with the highest number representing the most recent version. Note: When included in the request, the &#x60;fields&#x60; parameter is ignored. | [optional] 
 **properties** | [**list[str]**](str.md)| A list of issue properties to return for the issue. This parameter accepts a comma-separated list. Allowed values:   *  &#x60;*all&#x60; Returns all issue properties.  *  Any issue property key, prefixed with a minus to exclude.  Examples:   *  &#x60;*all&#x60; Returns all properties.  *  &#x60;*all,-prop1&#x60; Returns all properties except &#x60;prop1&#x60;.  *  &#x60;prop1,prop2&#x60; Returns &#x60;prop1&#x60; and &#x60;prop2&#x60; properties.  This parameter may be specified multiple times. For example, &#x60;properties&#x3D;prop1,prop2&amp; properties&#x3D;prop3&#x60;. | [optional] 
 **update_history** | **bool**| Whether the project in which the issue is created is added to the user&#x27;s **Recently viewed** project list, as shown under **Projects** in Jira. This also populates the [JQL issues search](#api-rest-api-3-search-get) &#x60;lastViewed&#x60; field. | [optional] [default to false]
 **fail_fast** | **bool**| Whether to fail the request quickly in case of an error while loading fields for an issue. For &#x60;failFast&#x3D;true&#x60;, if one field fails, the entire operation fails. For &#x60;failFast&#x3D;false&#x60;, the operation will continue even if a field fails. It will return a valid response, but without values for the failed field(s). | [optional] [default to false]

### Return type

[**IssueBean**](IssueBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_limit_report**
> IssueLimitReportResponseBean get_issue_limit_report(is_returning_keys=is_returning_keys)

Get issue limit report

Returns all issues breaching and approaching per-issue limits.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) is required for the project the issues are in. Results may be incomplete otherwise  *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
is_returning_keys = false # bool | Return issue keys instead of issue ids in the response.  Usage: Add `?isReturningKeys=true` to the end of the path to request issue keys. (optional) (default to false)

try:
    # Get issue limit report
    api_response = api_instance.get_issue_limit_report(is_returning_keys=is_returning_keys)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_issue_limit_report: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **is_returning_keys** | **bool**| Return issue keys instead of issue ids in the response.  Usage: Add &#x60;?isReturningKeys&#x3D;true&#x60; to the end of the path to request issue keys. | [optional] [default to false]

### Return type

[**IssueLimitReportResponseBean**](IssueLimitReportResponseBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_transitions**
> Transitions get_transitions(issue_id_or_key, expand=expand, transition_id=transition_id, skip_remote_only_condition=skip_remote_only_condition, include_unavailable_transitions=include_unavailable_transitions, sort_by_ops_bar_and_status=sort_by_ops_bar_and_status)

Get transitions

Returns either all transitions or a transition that can be performed by the user on an issue, based on the issue's status.  Note, if a request is made for a transition that does not exist or cannot be performed on the issue, given its status, the response will return any empty transitions list.  This operation can be accessed anonymously.  **[Permissions](#permissions) required: A list or transition is returned only when the user has:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.  However, if the user does not have the *Transition issues* [ project permission](https://confluence.atlassian.com/x/yodKLg) the response will not list any transitions.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about transitions in the response. This parameter accepts `transitions.fields`, which returns information about the fields in the transition screen for each transition. Fields hidden from the screen are not returned. Use this information to populate the `fields` and `update` fields in [Transition issue](#api-rest-api-3-issue-issueIdOrKey-transitions-post). (optional)
transition_id = 'transition_id_example' # str | The ID of the transition. (optional)
skip_remote_only_condition = false # bool | Whether transitions with the condition *Hide From User Condition* are included in the response. (optional) (default to false)
include_unavailable_transitions = false # bool | Whether details of transitions that fail a condition are included in the response (optional) (default to false)
sort_by_ops_bar_and_status = false # bool | Whether the transitions are sorted by ops-bar sequence value first then category order (Todo, In Progress, Done) or only by ops-bar sequence value. (optional) (default to false)

try:
    # Get transitions
    api_response = api_instance.get_transitions(issue_id_or_key, expand=expand, transition_id=transition_id, skip_remote_only_condition=skip_remote_only_condition, include_unavailable_transitions=include_unavailable_transitions, sort_by_ops_bar_and_status=sort_by_ops_bar_and_status)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->get_transitions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **expand** | **str**| Use [expand](#expansion) to include additional information about transitions in the response. This parameter accepts &#x60;transitions.fields&#x60;, which returns information about the fields in the transition screen for each transition. Fields hidden from the screen are not returned. Use this information to populate the &#x60;fields&#x60; and &#x60;update&#x60; fields in [Transition issue](#api-rest-api-3-issue-issueIdOrKey-transitions-post). | [optional] 
 **transition_id** | **str**| The ID of the transition. | [optional] 
 **skip_remote_only_condition** | **bool**| Whether transitions with the condition *Hide From User Condition* are included in the response. | [optional] [default to false]
 **include_unavailable_transitions** | **bool**| Whether details of transitions that fail a condition are included in the response | [optional] [default to false]
 **sort_by_ops_bar_and_status** | **bool**| Whether the transitions are sorted by ops-bar sequence value first then category order (Todo, In Progress, Done) or only by ops-bar sequence value. | [optional] [default to false]

### Return type

[**Transitions**](Transitions.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **notify**
> object notify(body, issue_id_or_key)

Send notification for issue

Creates an email notification for an issue and adds it to the mail queue.  **[Permissions](#permissions) required:**   *  *Browse Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = {
  "htmlBody" : "The <strong>latest</strong> test results for this ticket are now available.",
  "restrict" : {
    "groupIds" : [ ],
    "groups" : [ {
      "name" : "notification-group"
    } ],
    "permissions" : [ {
      "key" : "BROWSE"
    } ]
  },
  "subject" : "Latest test results",
  "textBody" : "The latest test results for this ticket are now available.",
  "to" : {
    "assignee" : false,
    "groupIds" : [ ],
    "groups" : [ {
      "name" : "notification-group"
    } ],
    "reporter" : false,
    "users" : [ {
      "accountId" : "5b10a2844c20165700ede21g",
      "active" : false
    } ],
    "voters" : true,
    "watchers" : true
  }
} # dict(str, object) | The request object for the notification and recipients.
issue_id_or_key = 'issue_id_or_key_example' # str | ID or key of the issue that the notification is sent for.

try:
    # Send notification for issue
    api_response = api_instance.notify(body, issue_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->notify: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)| The request object for the notification and recipients. | 
 **issue_id_or_key** | **str**| ID or key of the issue that the notification is sent for. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **unarchive_issues**
> IssueArchivalSyncResponse unarchive_issues(body)

Unarchive issue(s) by issue keys/ID

Enables admins to unarchive up to 1000 issues in a single request using issue ID/key, returning details of the issue(s) unarchived in the process and the errors encountered, if any.  **Note that:**   *  you can't unarchive subtasks directly, only through their parent issues  *  you can only unarchive issues from software, service management, and business projects  **[Permissions](#permissions) required:** Jira admin or site admin: [global permission](https://confluence.atlassian.com/x/x4dKLg)  **License required:** Premium or Enterprise  **Signed-in users only:** This API can't be accessed anonymously.     

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
api_instance = jira_client.IssuesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueArchivalSyncRequest() # IssueArchivalSyncRequest | Contains a list of issue keys or IDs to be unarchived.

try:
    # Unarchive issue(s) by issue keys/ID
    api_response = api_instance.unarchive_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssuesApi->unarchive_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueArchivalSyncRequest**](IssueArchivalSyncRequest.md)| Contains a list of issue keys or IDs to be unarchived. | 

### Return type

[**IssueArchivalSyncResponse**](IssueArchivalSyncResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

