# jira_client.JQLFunctionsAppsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_precomputations**](JQLFunctionsAppsApi.md#get_precomputations) | **GET** /rest/api/3/jql/function/computation | Get precomputations (apps)
[**get_precomputations_by_id**](JQLFunctionsAppsApi.md#get_precomputations_by_id) | **POST** /rest/api/3/jql/function/computation/search | Get precomputations by ID (apps)
[**update_precomputations**](JQLFunctionsAppsApi.md#update_precomputations) | **POST** /rest/api/3/jql/function/computation | Update precomputations (apps)

# **get_precomputations**
> PageBean2JqlFunctionPrecomputationBean get_precomputations(function_key=function_key, start_at=start_at, max_results=max_results, order_by=order_by)

Get precomputations (apps)

Returns the list of a function's precomputations along with information about when they were created, updated, and last used. Each precomputation has a `value` \\- the JQL fragment to replace the custom function clause with.  **[Permissions](#permissions) required:** This API is only accessible to apps and apps can only inspect their own functions.  The new `read:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.JQLFunctionsAppsApi(jira_client.ApiClient(configuration))
function_key = ['function_key_example'] # list[str] | The function key in format:   *  Forge: `ari:cloud:ecosystem::extension/[App ID]/[Environment ID]/static/[Function key from manifest]`  *  Connect: `[App key]__[Module key]` (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `functionKey` Sorts by the functionKey.  *  `used` Sorts by the used timestamp.  *  `created` Sorts by the created timestamp.  *  `updated` Sorts by the updated timestamp. (optional)

try:
    # Get precomputations (apps)
    api_response = api_instance.get_precomputations(function_key=function_key, start_at=start_at, max_results=max_results, order_by=order_by)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling JQLFunctionsAppsApi->get_precomputations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **function_key** | [**list[str]**](str.md)| The function key in format:   *  Forge: &#x60;ari:cloud:ecosystem::extension/[App ID]/[Environment ID]/static/[Function key from manifest]&#x60;  *  Connect: &#x60;[App key]__[Module key]&#x60; | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;functionKey&#x60; Sorts by the functionKey.  *  &#x60;used&#x60; Sorts by the used timestamp.  *  &#x60;created&#x60; Sorts by the created timestamp.  *  &#x60;updated&#x60; Sorts by the updated timestamp. | [optional] 

### Return type

[**PageBean2JqlFunctionPrecomputationBean**](PageBean2JqlFunctionPrecomputationBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_precomputations_by_id**
> JqlFunctionPrecomputationGetByIdResponse get_precomputations_by_id(body, order_by=order_by)

Get precomputations by ID (apps)

Returns function precomputations by IDs, along with information about when they were created, updated, and last used. Each precomputation has a `value` \\- the JQL fragment to replace the custom function clause with.  **[Permissions](#permissions) required:** This API is only accessible to apps and apps can only inspect their own functions.  The new `read:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.JQLFunctionsAppsApi(jira_client.ApiClient(configuration))
body = jira_client.JqlFunctionPrecomputationGetByIdRequest() # JqlFunctionPrecomputationGetByIdRequest | 
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `functionKey` Sorts by the functionKey.  *  `used` Sorts by the used timestamp.  *  `created` Sorts by the created timestamp.  *  `updated` Sorts by the updated timestamp. (optional)

try:
    # Get precomputations by ID (apps)
    api_response = api_instance.get_precomputations_by_id(body, order_by=order_by)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling JQLFunctionsAppsApi->get_precomputations_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**JqlFunctionPrecomputationGetByIdRequest**](JqlFunctionPrecomputationGetByIdRequest.md)|  | 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;functionKey&#x60; Sorts by the functionKey.  *  &#x60;used&#x60; Sorts by the used timestamp.  *  &#x60;created&#x60; Sorts by the created timestamp.  *  &#x60;updated&#x60; Sorts by the updated timestamp. | [optional] 

### Return type

[**JqlFunctionPrecomputationGetByIdResponse**](JqlFunctionPrecomputationGetByIdResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_precomputations**
> JqlFunctionPrecomputationUpdateResponse update_precomputations(body, skip_not_found_precomputations=skip_not_found_precomputations)

Update precomputations (apps)

Update the precomputation value of a function created by a Forge/Connect app.  **[Permissions](#permissions) required:** An API for apps to update their own precomputations.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.JQLFunctionsAppsApi(jira_client.ApiClient(configuration))
body = jira_client.JqlFunctionPrecomputationUpdateRequestBean() # JqlFunctionPrecomputationUpdateRequestBean | 
skip_not_found_precomputations = false # bool |  (optional) (default to false)

try:
    # Update precomputations (apps)
    api_response = api_instance.update_precomputations(body, skip_not_found_precomputations=skip_not_found_precomputations)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling JQLFunctionsAppsApi->update_precomputations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**JqlFunctionPrecomputationUpdateRequestBean**](JqlFunctionPrecomputationUpdateRequestBean.md)|  | 
 **skip_not_found_precomputations** | **bool**|  | [optional] [default to false]

### Return type

[**JqlFunctionPrecomputationUpdateResponse**](JqlFunctionPrecomputationUpdateResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

