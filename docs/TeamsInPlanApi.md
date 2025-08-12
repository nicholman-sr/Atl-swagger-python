# jira_client.TeamsInPlanApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_atlassian_team**](TeamsInPlanApi.md#add_atlassian_team) | **POST** /rest/api/3/plans/plan/{planId}/team/atlassian | Add Atlassian team to plan
[**create_plan_only_team**](TeamsInPlanApi.md#create_plan_only_team) | **POST** /rest/api/3/plans/plan/{planId}/team/planonly | Create plan-only team
[**delete_plan_only_team**](TeamsInPlanApi.md#delete_plan_only_team) | **DELETE** /rest/api/3/plans/plan/{planId}/team/planonly/{planOnlyTeamId} | Delete plan-only team
[**get_atlassian_team**](TeamsInPlanApi.md#get_atlassian_team) | **GET** /rest/api/3/plans/plan/{planId}/team/atlassian/{atlassianTeamId} | Get Atlassian team in plan
[**get_plan_only_team**](TeamsInPlanApi.md#get_plan_only_team) | **GET** /rest/api/3/plans/plan/{planId}/team/planonly/{planOnlyTeamId} | Get plan-only team
[**get_teams**](TeamsInPlanApi.md#get_teams) | **GET** /rest/api/3/plans/plan/{planId}/team | Get teams in plan paginated
[**remove_atlassian_team**](TeamsInPlanApi.md#remove_atlassian_team) | **DELETE** /rest/api/3/plans/plan/{planId}/team/atlassian/{atlassianTeamId} | Remove Atlassian team from plan
[**update_atlassian_team**](TeamsInPlanApi.md#update_atlassian_team) | **PUT** /rest/api/3/plans/plan/{planId}/team/atlassian/{atlassianTeamId} | Update Atlassian team in plan
[**update_plan_only_team**](TeamsInPlanApi.md#update_plan_only_team) | **PUT** /rest/api/3/plans/plan/{planId}/team/planonly/{planOnlyTeamId} | Update plan-only team

# **add_atlassian_team**
> object add_atlassian_team(body, plan_id)

Add Atlassian team to plan

Adds an existing Atlassian team to a plan and configures their plannning settings.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
body = jira_client.AddAtlassianTeamRequest() # AddAtlassianTeamRequest | 
plan_id = 789 # int | The ID of the plan.

try:
    # Add Atlassian team to plan
    api_response = api_instance.add_atlassian_team(body, plan_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->add_atlassian_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AddAtlassianTeamRequest**](AddAtlassianTeamRequest.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_plan_only_team**
> int create_plan_only_team(body, plan_id)

Create plan-only team

Creates a plan-only team and configures their planning settings.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
body = jira_client.CreatePlanOnlyTeamRequest() # CreatePlanOnlyTeamRequest | 
plan_id = 789 # int | The ID of the plan.

try:
    # Create plan-only team
    api_response = api_instance.create_plan_only_team(body, plan_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->create_plan_only_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CreatePlanOnlyTeamRequest**](CreatePlanOnlyTeamRequest.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 

### Return type

**int**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_plan_only_team**
> object delete_plan_only_team(plan_id, plan_only_team_id)

Delete plan-only team

Deletes a plan-only team and their planning settings.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
plan_only_team_id = 789 # int | The ID of the plan-only team.

try:
    # Delete plan-only team
    api_response = api_instance.delete_plan_only_team(plan_id, plan_only_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->delete_plan_only_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **plan_only_team_id** | **int**| The ID of the plan-only team. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_atlassian_team**
> GetAtlassianTeamResponse get_atlassian_team(plan_id, atlassian_team_id)

Get Atlassian team in plan

Returns planning settings for an Atlassian team in a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
atlassian_team_id = 'atlassian_team_id_example' # str | The ID of the Atlassian team.

try:
    # Get Atlassian team in plan
    api_response = api_instance.get_atlassian_team(plan_id, atlassian_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->get_atlassian_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **atlassian_team_id** | **str**| The ID of the Atlassian team. | 

### Return type

[**GetAtlassianTeamResponse**](GetAtlassianTeamResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_plan_only_team**
> GetPlanOnlyTeamResponse get_plan_only_team(plan_id, plan_only_team_id)

Get plan-only team

Returns planning settings for a plan-only team.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
plan_only_team_id = 789 # int | The ID of the plan-only team.

try:
    # Get plan-only team
    api_response = api_instance.get_plan_only_team(plan_id, plan_only_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->get_plan_only_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **plan_only_team_id** | **int**| The ID of the plan-only team. | 

### Return type

[**GetPlanOnlyTeamResponse**](GetPlanOnlyTeamResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_teams**
> PageWithCursorGetTeamResponseForPage get_teams(plan_id, cursor=cursor, max_results=max_results)

Get teams in plan paginated

Returns a [paginated](#pagination) list of plan-only and Atlassian teams in a plan.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
cursor = '' # str | The cursor to start from. If not provided, the first page will be returned. (optional)
max_results = 50 # int | The maximum number of plan teams to return per page. The maximum value is 50. The default value is 50. (optional) (default to 50)

try:
    # Get teams in plan paginated
    api_response = api_instance.get_teams(plan_id, cursor=cursor, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->get_teams: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **cursor** | **str**| The cursor to start from. If not provided, the first page will be returned. | [optional] 
 **max_results** | **int**| The maximum number of plan teams to return per page. The maximum value is 50. The default value is 50. | [optional] [default to 50]

### Return type

[**PageWithCursorGetTeamResponseForPage**](PageWithCursorGetTeamResponseForPage.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_atlassian_team**
> object remove_atlassian_team(plan_id, atlassian_team_id)

Remove Atlassian team from plan

Removes an Atlassian team from a plan and deletes their planning settings.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
plan_id = 789 # int | The ID of the plan.
atlassian_team_id = 'atlassian_team_id_example' # str | The ID of the Atlassian team.

try:
    # Remove Atlassian team from plan
    api_response = api_instance.remove_atlassian_team(plan_id, atlassian_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->remove_atlassian_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **plan_id** | **int**| The ID of the plan. | 
 **atlassian_team_id** | **str**| The ID of the Atlassian team. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_atlassian_team**
> object update_atlassian_team(body, plan_id, atlassian_team_id)

Update Atlassian team in plan

Updates any of the following planning settings of an Atlassian team in a plan using [JSON Patch](https://datatracker.ietf.org/doc/html/rfc6902).   *  planningStyle  *  issueSourceId  *  sprintLength  *  capacity  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *Note that \"add\" operations do not respect array indexes in target locations. Call the \"Get Atlassian team in plan\" endpoint to find out the order of array elements.*

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
body = "[{\"op\": \"replace\", \"path\": \"/planningStyle\", \"value\": \"Kanban\"}]\n" # object | 
plan_id = 789 # int | The ID of the plan.
atlassian_team_id = 'atlassian_team_id_example' # str | The ID of the Atlassian team.

try:
    # Update Atlassian team in plan
    api_response = api_instance.update_atlassian_team(body, plan_id, atlassian_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->update_atlassian_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 
 **atlassian_team_id** | **str**| The ID of the Atlassian team. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json-patch+json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_plan_only_team**
> object update_plan_only_team(body, plan_id, plan_only_team_id)

Update plan-only team

Updates any of the following planning settings of a plan-only team using [JSON Patch](https://datatracker.ietf.org/doc/html/rfc6902).   *  name  *  planningStyle  *  issueSourceId  *  sprintLength  *  capacity  *  memberAccountIds  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *Note that \"add\" operations do not respect array indexes in target locations. Call the \"Get plan-only team\" endpoint to find out the order of array elements.*

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
api_instance = jira_client.TeamsInPlanApi(jira_client.ApiClient(configuration))
body = "[{\"op\": \"replace\", \"path\": \"/planningStyle\", \"value\": \"Kanban\"}]\n" # object | 
plan_id = 789 # int | The ID of the plan.
plan_only_team_id = 789 # int | The ID of the plan-only team.

try:
    # Update plan-only team
    api_response = api_instance.update_plan_only_team(body, plan_id, plan_only_team_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TeamsInPlanApi->update_plan_only_team: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)|  | 
 **plan_id** | **int**| The ID of the plan. | 
 **plan_only_team_id** | **int**| The ID of the plan-only team. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json-patch+json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

