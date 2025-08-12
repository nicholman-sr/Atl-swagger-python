# jira_client.IssueRemoteLinksApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_or_update_remote_issue_link**](IssueRemoteLinksApi.md#create_or_update_remote_issue_link) | **POST** /rest/api/3/issue/{issueIdOrKey}/remotelink | Create or update remote issue link
[**delete_remote_issue_link_by_global_id**](IssueRemoteLinksApi.md#delete_remote_issue_link_by_global_id) | **DELETE** /rest/api/3/issue/{issueIdOrKey}/remotelink | Delete remote issue link by global ID
[**delete_remote_issue_link_by_id**](IssueRemoteLinksApi.md#delete_remote_issue_link_by_id) | **DELETE** /rest/api/3/issue/{issueIdOrKey}/remotelink/{linkId} | Delete remote issue link by ID
[**get_remote_issue_link_by_id**](IssueRemoteLinksApi.md#get_remote_issue_link_by_id) | **GET** /rest/api/3/issue/{issueIdOrKey}/remotelink/{linkId} | Get remote issue link by ID
[**get_remote_issue_links**](IssueRemoteLinksApi.md#get_remote_issue_links) | **GET** /rest/api/3/issue/{issueIdOrKey}/remotelink | Get remote issue links
[**update_remote_issue_link**](IssueRemoteLinksApi.md#update_remote_issue_link) | **PUT** /rest/api/3/issue/{issueIdOrKey}/remotelink/{linkId} | Update remote issue link by ID

# **create_or_update_remote_issue_link**
> RemoteIssueLinkIdentifies create_or_update_remote_issue_link(body, issue_id_or_key)

Create or update remote issue link

Creates or updates a remote issue link for an issue.  If a `globalId` is provided and a remote issue link with that global ID is found it is updated. Any fields without values in the request are set to null. Otherwise, the remote issue link is created.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Link issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
body = {
  "application" : {
    "name" : "My Acme Tracker",
    "type" : "com.acme.tracker"
  },
  "globalId" : "system=http://www.mycompany.com/support&id=1",
  "object" : {
    "icon" : {
      "title" : "Support Ticket",
      "url16x16" : "http://www.mycompany.com/support/ticket.png"
    },
    "status" : {
      "icon" : {
        "link" : "http://www.mycompany.com/support?id=1&details=closed",
        "title" : "Case Closed",
        "url16x16" : "http://www.mycompany.com/support/resolved.png"
      },
      "resolved" : true
    },
    "summary" : "Customer support issue",
    "title" : "TSTSUP-111",
    "url" : "http://www.mycompany.com/support?id=1"
  },
  "relationship" : "causes"
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.

try:
    # Create or update remote issue link
    api_response = api_instance.create_or_update_remote_issue_link(body, issue_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->create_or_update_remote_issue_link: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 

### Return type

[**RemoteIssueLinkIdentifies**](RemoteIssueLinkIdentifies.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_remote_issue_link_by_global_id**
> delete_remote_issue_link_by_global_id(issue_id_or_key, global_id)

Delete remote issue link by global ID

Deletes the remote issue link from the issue using the link's global ID. Where the global ID includes reserved URL characters these must be escaped in the request. For example, pass `system=http://www.mycompany.com/support&id=1` as `system%3Dhttp%3A%2F%2Fwww.mycompany.com%2Fsupport%26id%3D1`.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Link issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is implemented, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
global_id = 'global_id_example' # str | The global ID of a remote issue link.

try:
    # Delete remote issue link by global ID
    api_instance.delete_remote_issue_link_by_global_id(issue_id_or_key, global_id)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->delete_remote_issue_link_by_global_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **global_id** | **str**| The global ID of a remote issue link. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_remote_issue_link_by_id**
> delete_remote_issue_link_by_id(issue_id_or_key, link_id)

Delete remote issue link by ID

Deletes a remote issue link from an issue.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects*, *Edit issues*, and *Link issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
link_id = 'link_id_example' # str | The ID of a remote issue link.

try:
    # Delete remote issue link by ID
    api_instance.delete_remote_issue_link_by_id(issue_id_or_key, link_id)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->delete_remote_issue_link_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **link_id** | **str**| The ID of a remote issue link. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_remote_issue_link_by_id**
> RemoteIssueLink get_remote_issue_link_by_id(issue_id_or_key, link_id)

Get remote issue link by ID

Returns a remote issue link for an issue.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
link_id = 'link_id_example' # str | The ID of the remote issue link.

try:
    # Get remote issue link by ID
    api_response = api_instance.get_remote_issue_link_by_id(issue_id_or_key, link_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->get_remote_issue_link_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **link_id** | **str**| The ID of the remote issue link. | 

### Return type

[**RemoteIssueLink**](RemoteIssueLink.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_remote_issue_links**
> RemoteIssueLink get_remote_issue_links(issue_id_or_key, global_id=global_id)

Get remote issue links

Returns the remote issue links for an issue. When a remote issue link global ID is provided the record with that global ID is returned, otherwise all remote issue links are returned. Where a global ID includes reserved URL characters these must be escaped in the request. For example, pass `system=http://www.mycompany.com/support&id=1` as `system%3Dhttp%3A%2F%2Fwww.mycompany.com%2Fsupport%26id%3D1`.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
global_id = 'global_id_example' # str | The global ID of the remote issue link. (optional)

try:
    # Get remote issue links
    api_response = api_instance.get_remote_issue_links(issue_id_or_key, global_id=global_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->get_remote_issue_links: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **global_id** | **str**| The global ID of the remote issue link. | [optional] 

### Return type

[**RemoteIssueLink**](RemoteIssueLink.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_remote_issue_link**
> object update_remote_issue_link(body, issue_id_or_key, link_id)

Update remote issue link by ID

Updates a remote issue link for an issue.  Note: Fields without values in the request are set to null.  This operation requires [issue linking to be active](https://confluence.atlassian.com/x/yoXKM).  This operation can be accessed anonymously.  **[Permissions](#permissions) required:**   *  *Browse projects* and *Link issues* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueRemoteLinksApi(jira_client.ApiClient(configuration))
body = {
  "application" : {
    "name" : "My Acme Tracker",
    "type" : "com.acme.tracker"
  },
  "globalId" : "system=http://www.mycompany.com/support&id=1",
  "object" : {
    "icon" : {
      "title" : "Support Ticket",
      "url16x16" : "http://www.mycompany.com/support/ticket.png"
    },
    "status" : {
      "icon" : {
        "link" : "http://www.mycompany.com/support?id=1&details=closed",
        "title" : "Case Closed",
        "url16x16" : "http://www.mycompany.com/support/resolved.png"
      },
      "resolved" : true
    },
    "summary" : "Customer support issue",
    "title" : "TSTSUP-111",
    "url" : "http://www.mycompany.com/support?id=1"
  },
  "relationship" : "causes"
} # dict(str, object) | 
issue_id_or_key = 'issue_id_or_key_example' # str | The ID or key of the issue.
link_id = 'link_id_example' # str | The ID of the remote issue link.

try:
    # Update remote issue link by ID
    api_response = api_instance.update_remote_issue_link(body, issue_id_or_key, link_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRemoteLinksApi->update_remote_issue_link: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **issue_id_or_key** | **str**| The ID or key of the issue. | 
 **link_id** | **str**| The ID of the remote issue link. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

