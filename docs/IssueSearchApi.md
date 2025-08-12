# jira_client.IssueSearchApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**count_issues**](IssueSearchApi.md#count_issues) | **POST** /rest/api/3/search/approximate-count | Count issues using JQL
[**get_issue_picker_resource**](IssueSearchApi.md#get_issue_picker_resource) | **GET** /rest/api/3/issue/picker | Get issue picker suggestions
[**match_issues**](IssueSearchApi.md#match_issues) | **POST** /rest/api/3/jql/match | Check issues against JQL
[**search_and_reconsile_issues_using_jql**](IssueSearchApi.md#search_and_reconsile_issues_using_jql) | **GET** /rest/api/3/search/jql | Search for issues using JQL enhanced search (GET)
[**search_and_reconsile_issues_using_jql_post**](IssueSearchApi.md#search_and_reconsile_issues_using_jql_post) | **POST** /rest/api/3/search/jql | Search for issues using JQL enhanced search (POST)
[**search_for_issues_using_jql**](IssueSearchApi.md#search_for_issues_using_jql) | **GET** /rest/api/3/search | Currently being removed. Search for issues using JQL (GET)
[**search_for_issues_using_jql_post**](IssueSearchApi.md#search_for_issues_using_jql_post) | **POST** /rest/api/3/search | Currently being removed. Search for issues using JQL (POST)

# **count_issues**
> JQLCountResultsBean count_issues(body)

Count issues using JQL

Provide an estimated count of the issues that match the [JQL](https://confluence.atlassian.com/x/egORLQ). Recent updates might not be immediately visible in the returned output. This endpoint requires JQL to be bounded.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
body = jira_client.JQLCountRequestBean() # JQLCountRequestBean | A JSON object containing the search request.

try:
    # Count issues using JQL
    api_response = api_instance.count_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->count_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**JQLCountRequestBean**](JQLCountRequestBean.md)| A JSON object containing the search request. | 

### Return type

[**JQLCountResultsBean**](JQLCountResultsBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_picker_resource**
> IssuePickerSuggestions get_issue_picker_resource(query=query, current_jql=current_jql, current_issue_key=current_issue_key, current_project_id=current_project_id, show_sub_tasks=show_sub_tasks, show_sub_task_parent=show_sub_task_parent)

Get issue picker suggestions

Returns lists of issues matching a query string. Use this resource to provide auto-completion suggestions when the user is looking for an issue using a word or string.  This operation returns two lists:   *  `History Search` which includes issues from the user's history of created, edited, or viewed issues that contain the string in the `query` parameter.  *  `Current Search` which includes issues that match the JQL expression in `currentJQL` and contain the string in the `query` parameter.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
query = 'query_example' # str | A string to match against text fields in the issue such as title, description, or comments. (optional)
current_jql = 'current_jql_example' # str | A JQL query defining a list of issues to search for the query term. Note that `username` and `userkey` cannot be used as search terms for this parameter, due to privacy reasons. Use `accountId` instead. (optional)
current_issue_key = 'current_issue_key_example' # str | The key of an issue to exclude from search results. For example, the issue the user is viewing when they perform this query. (optional)
current_project_id = 'current_project_id_example' # str | The ID of a project that suggested issues must belong to. (optional)
show_sub_tasks = true # bool | Indicate whether to include subtasks in the suggestions list. (optional)
show_sub_task_parent = true # bool | When `currentIssueKey` is a subtask, whether to include the parent issue in the suggestions if it matches the query. (optional)

try:
    # Get issue picker suggestions
    api_response = api_instance.get_issue_picker_resource(query=query, current_jql=current_jql, current_issue_key=current_issue_key, current_project_id=current_project_id, show_sub_tasks=show_sub_tasks, show_sub_task_parent=show_sub_task_parent)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->get_issue_picker_resource: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **query** | **str**| A string to match against text fields in the issue such as title, description, or comments. | [optional] 
 **current_jql** | **str**| A JQL query defining a list of issues to search for the query term. Note that &#x60;username&#x60; and &#x60;userkey&#x60; cannot be used as search terms for this parameter, due to privacy reasons. Use &#x60;accountId&#x60; instead. | [optional] 
 **current_issue_key** | **str**| The key of an issue to exclude from search results. For example, the issue the user is viewing when they perform this query. | [optional] 
 **current_project_id** | **str**| The ID of a project that suggested issues must belong to. | [optional] 
 **show_sub_tasks** | **bool**| Indicate whether to include subtasks in the suggestions list. | [optional] 
 **show_sub_task_parent** | **bool**| When &#x60;currentIssueKey&#x60; is a subtask, whether to include the parent issue in the suggestions if it matches the query. | [optional] 

### Return type

[**IssuePickerSuggestions**](IssuePickerSuggestions.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **match_issues**
> IssueMatches match_issues(body)

Check issues against JQL

Checks whether one or more issues would be returned by one or more JQL queries.  **[Permissions](#permissions) required:** None, however, issues are only matched against JQL queries where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project that the issue is in.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
body = jira_client.IssuesAndJQLQueries() # IssuesAndJQLQueries | 

try:
    # Check issues against JQL
    api_response = api_instance.match_issues(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->match_issues: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssuesAndJQLQueries**](IssuesAndJQLQueries.md)|  | 

### Return type

[**IssueMatches**](IssueMatches.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_and_reconsile_issues_using_jql**
> SearchAndReconcileResults search_and_reconsile_issues_using_jql(jql=jql, next_page_token=next_page_token, max_results=max_results, fields=fields, expand=expand, properties=properties, fields_by_keys=fields_by_keys, fail_fast=fail_fast, reconcile_issues=reconcile_issues)

Search for issues using JQL enhanced search (GET)

Searches for issues using [JQL](https://confluence.atlassian.com/x/egORLQ). Recent updates might not be immediately visible in the returned search results. If you need [read-after-write](https://developer.atlassian.com/cloud/jira/platform/search-and-reconcile/) consistency, you can utilize the `reconcileIssues` parameter to ensure stronger consistency assurances. This operation can be accessed anonymously.  If the JQL query expression is too large to be encoded as a query parameter, use the [POST](#api-rest-api-3-search-post) version of this resource.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
jql = 'jql_example' # str | A [JQL](https://confluence.atlassian.com/x/egORLQ) expression. For performance reasons, this parameter requires a bounded query. A bounded query is a query with a search restriction.   *  Example of an unbounded query: `order by key desc`.  *  Example of a bounded query: `assignee = currentUser() order by key`.  Additionally, `orderBy` clause can contain a maximum of 7 fields. (optional)
next_page_token = 'next_page_token_example' # str | The token for a page to fetch that is not the first page. The first page has a `nextPageToken` of `null`. Use the `nextPageToken` to fetch the next page of issues.  Note: The `nextPageToken` field is **not included** in the response for the last page, indicating there is no next page. (optional)
max_results = 50 # int | The maximum number of items to return per page. To manage page size, API may return fewer items per page where a large number of fields or properties are requested. The greatest number of items returned per page is achieved when requesting `id` or `key` only. It returns max 5000 issues. (optional) (default to 50)
fields = ['fields_example'] # list[str] | A list of fields to return for each issue, use it to retrieve a subset of fields. This parameter accepts a comma-separated list. Expand options include:   *  `*all` Returns all fields.  *  `*navigable` Returns navigable fields.  *  `id` Returns only issue IDs.  *  Any issue field, prefixed with a minus to exclude.  The default is `id`.  Examples:   *  `summary,comment` Returns only the summary and comments fields only.  *  `-description` Returns all navigable (default) fields except description.  *  `*all,-comment` Returns all fields except comments.  Multiple `fields` parameters can be included in a request.  Note: By default, this resource returns IDs only. This differs from [GET issue](#api-rest-api-3-issue-issueIdOrKey-get) where the default is all fields. (optional)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about issues in the response. Note that, unlike the majority of instances where `expand` is specified, `expand` is defined as a comma-delimited string of values. The expand options are:   *  `renderedFields` Returns field values rendered in HTML format.  *  `names` Returns the display name of each field.  *  `schema` Returns the schema describing a field type.  *  `transitions` Returns all possible transitions for the issue.  *  `operations` Returns all possible operations for the issue.  *  `editmeta` Returns information about how each field can be edited.  *  `changelog` Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  `versionedRepresentations` Instead of `fields`, returns `versionedRepresentations` a JSON array containing each version of a field's value, with the highest numbered item representing the most recent version.  Examples: `\"names,changelog\"` Returns the display name of each field as well as a list of recent updates to an issue. (optional)
properties = ['properties_example'] # list[str] | A list of up to 5 issue properties to include in the results. This parameter accepts a comma-separated list. (optional)
fields_by_keys = false # bool | Reference fields by their key (rather than ID). The default is `false`. (optional) (default to false)
fail_fast = false # bool | Fail this request early if we can't retrieve all field data. (optional) (default to false)
reconcile_issues = [56] # list[int] | Strong consistency issue ids to be reconciled with search results. Accepts max 50 ids (optional)

try:
    # Search for issues using JQL enhanced search (GET)
    api_response = api_instance.search_and_reconsile_issues_using_jql(jql=jql, next_page_token=next_page_token, max_results=max_results, fields=fields, expand=expand, properties=properties, fields_by_keys=fields_by_keys, fail_fast=fail_fast, reconcile_issues=reconcile_issues)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->search_and_reconsile_issues_using_jql: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jql** | **str**| A [JQL](https://confluence.atlassian.com/x/egORLQ) expression. For performance reasons, this parameter requires a bounded query. A bounded query is a query with a search restriction.   *  Example of an unbounded query: &#x60;order by key desc&#x60;.  *  Example of a bounded query: &#x60;assignee &#x3D; currentUser() order by key&#x60;.  Additionally, &#x60;orderBy&#x60; clause can contain a maximum of 7 fields. | [optional] 
 **next_page_token** | **str**| The token for a page to fetch that is not the first page. The first page has a &#x60;nextPageToken&#x60; of &#x60;null&#x60;. Use the &#x60;nextPageToken&#x60; to fetch the next page of issues.  Note: The &#x60;nextPageToken&#x60; field is **not included** in the response for the last page, indicating there is no next page. | [optional] 
 **max_results** | **int**| The maximum number of items to return per page. To manage page size, API may return fewer items per page where a large number of fields or properties are requested. The greatest number of items returned per page is achieved when requesting &#x60;id&#x60; or &#x60;key&#x60; only. It returns max 5000 issues. | [optional] [default to 50]
 **fields** | [**list[str]**](str.md)| A list of fields to return for each issue, use it to retrieve a subset of fields. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;*all&#x60; Returns all fields.  *  &#x60;*navigable&#x60; Returns navigable fields.  *  &#x60;id&#x60; Returns only issue IDs.  *  Any issue field, prefixed with a minus to exclude.  The default is &#x60;id&#x60;.  Examples:   *  &#x60;summary,comment&#x60; Returns only the summary and comments fields only.  *  &#x60;-description&#x60; Returns all navigable (default) fields except description.  *  &#x60;*all,-comment&#x60; Returns all fields except comments.  Multiple &#x60;fields&#x60; parameters can be included in a request.  Note: By default, this resource returns IDs only. This differs from [GET issue](#api-rest-api-3-issue-issueIdOrKey-get) where the default is all fields. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about issues in the response. Note that, unlike the majority of instances where &#x60;expand&#x60; is specified, &#x60;expand&#x60; is defined as a comma-delimited string of values. The expand options are:   *  &#x60;renderedFields&#x60; Returns field values rendered in HTML format.  *  &#x60;names&#x60; Returns the display name of each field.  *  &#x60;schema&#x60; Returns the schema describing a field type.  *  &#x60;transitions&#x60; Returns all possible transitions for the issue.  *  &#x60;operations&#x60; Returns all possible operations for the issue.  *  &#x60;editmeta&#x60; Returns information about how each field can be edited.  *  &#x60;changelog&#x60; Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  &#x60;versionedRepresentations&#x60; Instead of &#x60;fields&#x60;, returns &#x60;versionedRepresentations&#x60; a JSON array containing each version of a field&#x27;s value, with the highest numbered item representing the most recent version.  Examples: &#x60;\&quot;names,changelog\&quot;&#x60; Returns the display name of each field as well as a list of recent updates to an issue. | [optional] 
 **properties** | [**list[str]**](str.md)| A list of up to 5 issue properties to include in the results. This parameter accepts a comma-separated list. | [optional] 
 **fields_by_keys** | **bool**| Reference fields by their key (rather than ID). The default is &#x60;false&#x60;. | [optional] [default to false]
 **fail_fast** | **bool**| Fail this request early if we can&#x27;t retrieve all field data. | [optional] [default to false]
 **reconcile_issues** | [**list[int]**](int.md)| Strong consistency issue ids to be reconciled with search results. Accepts max 50 ids | [optional] 

### Return type

[**SearchAndReconcileResults**](SearchAndReconcileResults.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_and_reconsile_issues_using_jql_post**
> SearchAndReconcileResults search_and_reconsile_issues_using_jql_post(body)

Search for issues using JQL enhanced search (POST)

Searches for issues using [JQL](https://confluence.atlassian.com/x/egORLQ). Recent updates might not be immediately visible in the returned search results. If you need [read-after-write](https://developer.atlassian.com/cloud/jira/platform/search-and-reconcile/) consistency, you can utilize the `reconcileIssues` parameter to ensure stronger consistency assurances. This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
body = jira_client.SearchAndReconcileRequestBean() # SearchAndReconcileRequestBean | 

try:
    # Search for issues using JQL enhanced search (POST)
    api_response = api_instance.search_and_reconsile_issues_using_jql_post(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->search_and_reconsile_issues_using_jql_post: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SearchAndReconcileRequestBean**](SearchAndReconcileRequestBean.md)|  | 

### Return type

[**SearchAndReconcileResults**](SearchAndReconcileResults.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_for_issues_using_jql**
> SearchResults search_for_issues_using_jql(jql=jql, start_at=start_at, max_results=max_results, validate_query=validate_query, fields=fields, expand=expand, properties=properties, fields_by_keys=fields_by_keys, fail_fast=fail_fast)

Currently being removed. Search for issues using JQL (GET)

Endpoint is currently being removed. [More details](https://developer.atlassian.com/changelog/#CHANGE-2046)  Searches for issues using [JQL](https://confluence.atlassian.com/x/egORLQ).  If the JQL query expression is too large to be encoded as a query parameter, use the [POST](#api-rest-api-3-search-post) version of this resource.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
jql = 'jql_example' # str | The [JQL](https://confluence.atlassian.com/x/egORLQ) that defines the search. Note:   *  If no JQL expression is provided, all issues are returned.  *  `username` and `userkey` cannot be used as search terms due to privacy reasons. Use `accountId` instead.  *  If a user has hidden their email address in their user profile, partial matches of the email address will not find the user. An exact match is required. (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. To manage page size, Jira may return fewer items per page where a large number of fields or properties are requested. The greatest number of items returned per page is achieved when requesting `id` or `key` only. (optional) (default to 50)
validate_query = 'strict' # str | Determines how to validate the JQL query and treat the validation results. Supported values are:   *  `strict` Returns a 400 response code if any errors are found, along with a list of all errors (and warnings).  *  `warn` Returns all errors as warnings.  *  `none` No validation is performed.  *  `true` *Deprecated* A legacy synonym for `strict`.  *  `false` *Deprecated* A legacy synonym for `warn`.  Note: If the JQL is not correctly formed a 400 response code is returned, regardless of the `validateQuery` value. (optional) (default to strict)
fields = ['fields_example'] # list[str] | A list of fields to return for each issue, use it to retrieve a subset of fields. This parameter accepts a comma-separated list. Expand options include:   *  `*all` Returns all fields.  *  `*navigable` Returns navigable fields.  *  Any issue field, prefixed with a minus to exclude.  Examples:   *  `summary,comment` Returns only the summary and comments fields.  *  `-description` Returns all navigable (default) fields except description.  *  `*all,-comment` Returns all fields except comments.  This parameter may be specified multiple times. For example, `fields=field1,field2&fields=field3`.  Note: All navigable fields are returned by default. This differs from [GET issue](#api-rest-api-3-issue-issueIdOrKey-get) where the default is all fields. (optional)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about issues in the response. This parameter accepts a comma-separated list. Expand options include:   *  `renderedFields` Returns field values rendered in HTML format.  *  `names` Returns the display name of each field.  *  `schema` Returns the schema describing a field type.  *  `transitions` Returns all possible transitions for the issue.  *  `operations` Returns all possible operations for the issue.  *  `editmeta` Returns information about how each field can be edited.  *  `changelog` Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  `versionedRepresentations` Instead of `fields`, returns `versionedRepresentations` a JSON array containing each version of a field's value, with the highest numbered item representing the most recent version. (optional)
properties = ['properties_example'] # list[str] | A list of issue property keys for issue properties to include in the results. This parameter accepts a comma-separated list. Multiple properties can also be provided using an ampersand separated list. For example, `properties=prop1,prop2&properties=prop3`. A maximum of 5 issue property keys can be specified. (optional)
fields_by_keys = false # bool | Reference fields by their key (rather than ID). (optional) (default to false)
fail_fast = false # bool | Whether to fail the request quickly in case of an error while loading fields for an issue. For `failFast=true`, if one field fails, the entire operation fails. For `failFast=false`, the operation will continue even if a field fails. It will return a valid response, but without values for the failed field(s). (optional) (default to false)

try:
    # Currently being removed. Search for issues using JQL (GET)
    api_response = api_instance.search_for_issues_using_jql(jql=jql, start_at=start_at, max_results=max_results, validate_query=validate_query, fields=fields, expand=expand, properties=properties, fields_by_keys=fields_by_keys, fail_fast=fail_fast)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->search_for_issues_using_jql: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **jql** | **str**| The [JQL](https://confluence.atlassian.com/x/egORLQ) that defines the search. Note:   *  If no JQL expression is provided, all issues are returned.  *  &#x60;username&#x60; and &#x60;userkey&#x60; cannot be used as search terms due to privacy reasons. Use &#x60;accountId&#x60; instead.  *  If a user has hidden their email address in their user profile, partial matches of the email address will not find the user. An exact match is required. | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. To manage page size, Jira may return fewer items per page where a large number of fields or properties are requested. The greatest number of items returned per page is achieved when requesting &#x60;id&#x60; or &#x60;key&#x60; only. | [optional] [default to 50]
 **validate_query** | **str**| Determines how to validate the JQL query and treat the validation results. Supported values are:   *  &#x60;strict&#x60; Returns a 400 response code if any errors are found, along with a list of all errors (and warnings).  *  &#x60;warn&#x60; Returns all errors as warnings.  *  &#x60;none&#x60; No validation is performed.  *  &#x60;true&#x60; *Deprecated* A legacy synonym for &#x60;strict&#x60;.  *  &#x60;false&#x60; *Deprecated* A legacy synonym for &#x60;warn&#x60;.  Note: If the JQL is not correctly formed a 400 response code is returned, regardless of the &#x60;validateQuery&#x60; value. | [optional] [default to strict]
 **fields** | [**list[str]**](str.md)| A list of fields to return for each issue, use it to retrieve a subset of fields. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;*all&#x60; Returns all fields.  *  &#x60;*navigable&#x60; Returns navigable fields.  *  Any issue field, prefixed with a minus to exclude.  Examples:   *  &#x60;summary,comment&#x60; Returns only the summary and comments fields.  *  &#x60;-description&#x60; Returns all navigable (default) fields except description.  *  &#x60;*all,-comment&#x60; Returns all fields except comments.  This parameter may be specified multiple times. For example, &#x60;fields&#x3D;field1,field2&amp;fields&#x3D;field3&#x60;.  Note: All navigable fields are returned by default. This differs from [GET issue](#api-rest-api-3-issue-issueIdOrKey-get) where the default is all fields. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information about issues in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;renderedFields&#x60; Returns field values rendered in HTML format.  *  &#x60;names&#x60; Returns the display name of each field.  *  &#x60;schema&#x60; Returns the schema describing a field type.  *  &#x60;transitions&#x60; Returns all possible transitions for the issue.  *  &#x60;operations&#x60; Returns all possible operations for the issue.  *  &#x60;editmeta&#x60; Returns information about how each field can be edited.  *  &#x60;changelog&#x60; Returns a list of recent updates to an issue, sorted by date, starting from the most recent.  *  &#x60;versionedRepresentations&#x60; Instead of &#x60;fields&#x60;, returns &#x60;versionedRepresentations&#x60; a JSON array containing each version of a field&#x27;s value, with the highest numbered item representing the most recent version. | [optional] 
 **properties** | [**list[str]**](str.md)| A list of issue property keys for issue properties to include in the results. This parameter accepts a comma-separated list. Multiple properties can also be provided using an ampersand separated list. For example, &#x60;properties&#x3D;prop1,prop2&amp;properties&#x3D;prop3&#x60;. A maximum of 5 issue property keys can be specified. | [optional] 
 **fields_by_keys** | **bool**| Reference fields by their key (rather than ID). | [optional] [default to false]
 **fail_fast** | **bool**| Whether to fail the request quickly in case of an error while loading fields for an issue. For &#x60;failFast&#x3D;true&#x60;, if one field fails, the entire operation fails. For &#x60;failFast&#x3D;false&#x60;, the operation will continue even if a field fails. It will return a valid response, but without values for the failed field(s). | [optional] [default to false]

### Return type

[**SearchResults**](SearchResults.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_for_issues_using_jql_post**
> SearchResults search_for_issues_using_jql_post(body)

Currently being removed. Search for issues using JQL (POST)

Endpoint is currently being removed. [More details](https://developer.atlassian.com/changelog/#CHANGE-2046)  Searches for issues using [JQL](https://confluence.atlassian.com/x/egORLQ).  There is a [GET](#api-rest-api-3-search-get) version of this resource that can be used for smaller JQL query expressions.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** Issues are included in the response where the user has:   *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for the project containing the issue.  *  If [issue-level security](https://confluence.atlassian.com/x/J4lKLg) is configured, issue-level security permission to view the issue.

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
api_instance = jira_client.IssueSearchApi(jira_client.ApiClient(configuration))
body = jira_client.SearchRequestBean() # SearchRequestBean | A JSON object containing the search request.

try:
    # Currently being removed. Search for issues using JQL (POST)
    api_response = api_instance.search_for_issues_using_jql_post(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSearchApi->search_for_issues_using_jql_post: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SearchRequestBean**](SearchRequestBean.md)| A JSON object containing the search request. | 

### Return type

[**SearchResults**](SearchResults.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

