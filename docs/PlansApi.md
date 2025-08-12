# jira_client.PlansApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**archive_plan**](PlansApi.md#archive_plan) | **PUT** /rest/api/3/plans/plan/{planId}/archive | Archive plan
[**create_plan**](PlansApi.md#create_plan) | **POST** /rest/api/3/plans/plan | Create plan
[**duplicate_plan**](PlansApi.md#duplicate_plan) | **POST** /rest/api/3/plans/plan/{planId}/duplicate | Duplicate plan
[**get_plan**](PlansApi.md#get_plan) | **GET** /rest/api/3/plans/plan/{planId} | Get plan
[**get_plans**](PlansApi.md#get_plans) | **GET** /rest/api/3/plans/plan | Get plans paginated
[**trash_plan**](PlansApi.md#trash_plan) | **PUT** /rest/api/3/plans/plan/{planId}/trash | Trash plan
[**update_plan**](PlansApi.md#update_plan) | **PUT** /rest/api/3/plans/plan/{planId} | Update plan

# **archive_plan**
> object archive_plan(plan_id)

Archive plan

Archives a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.

try:
    # Archive plan
    api_response = api_instance.archive_plan(plan_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->archive_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_plan**
> int create_plan(body, use_group_id=use_group_id)

Create plan

Creates a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
body = jira_client.CreatePlanRequest() # CreatePlanRequest | 
use_group_id = false # bool | Whether to accept group IDs instead of group names. Group names are deprecated. (optional) (default to false)

try:
    # Create plan
    api_response = api_instance.create_plan(body, use_group_id=use_group_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->create_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CreatePlanRequest**](CreatePlanRequest.md)|  | 
 **use_group_id** | **bool**| Whether to accept group IDs instead of group names. Group names are deprecated. | [optional] [default to false]

### Return type

**int**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **duplicate_plan**
> int duplicate_plan(body, plan_id)

Duplicate plan

Duplicates a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
body = jira_client.DuplicatePlanRequest() # DuplicatePlanRequest | 
plan_id = 789 # int | The ID of the plan.

try:
    # Duplicate plan
    api_response = api_instance.duplicate_plan(body, plan_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->duplicate_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DuplicatePlanRequest**](DuplicatePlanRequest.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 

### Return type

**int**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_plan**
> GetPlanResponse get_plan(plan_id, use_group_id=use_group_id)

Get plan

Returns a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
use_group_id = false # bool | Whether to return group IDs instead of group names. Group names are deprecated. (optional) (default to false)

try:
    # Get plan
    api_response = api_instance.get_plan(plan_id, use_group_id=use_group_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->get_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **use_group_id** | **bool**| Whether to return group IDs instead of group names. Group names are deprecated. | [optional] [default to false]

### Return type

[**GetPlanResponse**](GetPlanResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_plans**
> PageWithCursorGetPlanResponseForPage get_plans(include_trashed=include_trashed, include_archived=include_archived, cursor=cursor, max_results=max_results)

Get plans paginated

Returns a [paginated](#pagination) list of plans.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
include_trashed = false # bool | Whether to include trashed plans in the results. (optional) (default to false)
include_archived = false # bool | Whether to include archived plans in the results. (optional) (default to false)
cursor = '' # str | The cursor to start from. If not provided, the first page will be returned. (optional)
max_results = 50 # int | The maximum number of plans to return per page. The maximum value is 50. The default value is 50. (optional) (default to 50)

try:
    # Get plans paginated
    api_response = api_instance.get_plans(include_trashed=include_trashed, include_archived=include_archived, cursor=cursor, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->get_plans: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **include_trashed** | **bool**| Whether to include trashed plans in the results. | [optional] [default to false]
 **include_archived** | **bool**| Whether to include archived plans in the results. | [optional] [default to false]
 **cursor** | **str**| The cursor to start from. If not provided, the first page will be returned. | [optional] 
 **max_results** | **int**| The maximum number of plans to return per page. The maximum value is 50. The default value is 50. | [optional] [default to 50]

### Return type

[**PageWithCursorGetPlanResponseForPage**](PageWithCursorGetPlanResponseForPage.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **trash_plan**
> object trash_plan(plan_id)

Trash plan

Moves a plan to trash.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.

try:
    # Trash plan
    api_response = api_instance.trash_plan(plan_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->trash_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_plan**
> object update_plan(body, plan_id, use_group_id=use_group_id)

Update plan

Updates any of the following details of a plan using [JSON Patch](https://datatracker.ietf.org/doc/html/rfc6902).   *  name  *  leadAccountId  *  scheduling           *  estimation with StoryPoints, Days or Hours as possible values      *  startDate                   *  type with DueDate, TargetStartDate, TargetEndDate or DateCustomField as possible values          *  dateCustomFieldId      *  endDate                   *  type with DueDate, TargetStartDate, TargetEndDate or DateCustomField as possible values          *  dateCustomFieldId      *  inferredDates with None, SprintDates or ReleaseDates as possible values      *  dependencies with Sequential or Concurrent as possible values  *  issueSources           *  type with Board, Project or Filter as possible values      *  value  *  exclusionRules           *  numberOfDaysToShowCompletedIssues      *  issueIds      *  workStatusIds      *  workStatusCategoryIds      *  issueTypeIds      *  releaseIds  *  crossProjectReleases           *  name      *  releaseIds  *  customFields           *  customFieldId      *  filter  *  permissions           *  type with View or Edit as possible values      *  holder                   *  type with Group or AccountId as possible values          *  value  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *Note that \"add\" operations do not respect array indexes in target locations. Call the \"Get plan\" endpoint to find out the order of array elements.*

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
api_instance = jira_client.PlansApi(jira_client.ApiClient(configuration))
body = "[{\"op\": \"replace\", \"path\": \"/scheduling/estimation\", \"value\": \"Days\"}]\n" # object | 
plan_id = 789 # int | The ID of the plan.
use_group_id = false # bool | Whether to accept group IDs instead of group names. Group names are deprecated. (optional) (default to false)

try:
    # Update plan
    api_response = api_instance.update_plan(body, plan_id, use_group_id=use_group_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PlansApi->update_plan: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 
 **use_group_id** | **bool**| Whether to accept group IDs instead of group names. Group names are deprecated. | [optional] [default to false]

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json-patch+json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

