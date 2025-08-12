# jira_client.ScreenSchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_screen_scheme**](ScreenSchemesApi.md#create_screen_scheme) | **POST** /rest/api/3/screenscheme | Create screen scheme
[**delete_screen_scheme**](ScreenSchemesApi.md#delete_screen_scheme) | **DELETE** /rest/api/3/screenscheme/{screenSchemeId} | Delete screen scheme
[**get_screen_schemes**](ScreenSchemesApi.md#get_screen_schemes) | **GET** /rest/api/3/screenscheme | Get screen schemes
[**update_screen_scheme**](ScreenSchemesApi.md#update_screen_scheme) | **PUT** /rest/api/3/screenscheme/{screenSchemeId} | Update screen scheme

# **create_screen_scheme**
> ScreenSchemeId create_screen_scheme(body)

Create screen scheme

Creates a screen scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.ScreenSchemeDetails() # ScreenSchemeDetails | 

try:
    # Create screen scheme
    api_response = api_instance.create_screen_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenSchemesApi->create_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ScreenSchemeDetails**](ScreenSchemeDetails.md)|  | 

### Return type

[**ScreenSchemeId**](ScreenSchemeId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_screen_scheme**
> delete_screen_scheme(screen_scheme_id)

Delete screen scheme

Deletes a screen scheme. A screen scheme cannot be deleted if it is used in an issue type screen scheme.  Only screens schemes used in classic projects can be deleted.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenSchemesApi(jira_client.ApiClient(configuration))
screen_scheme_id = 'screen_scheme_id_example' # str | The ID of the screen scheme.

try:
    # Delete screen scheme
    api_instance.delete_screen_scheme(screen_scheme_id)
except ApiException as e:
    print("Exception when calling ScreenSchemesApi->delete_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_scheme_id** | **str**| The ID of the screen scheme. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screen_schemes**
> PageBeanScreenScheme get_screen_schemes(start_at=start_at, max_results=max_results, id=id, expand=expand, query_string=query_string, order_by=order_by)

Get screen schemes

Returns a [paginated](#pagination) list of screen schemes.  Only screen schemes used in classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenSchemesApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 25 # int | The maximum number of items to return per page. (optional) (default to 25)
id = [56] # list[int] | The list of screen scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, `id=10000&id=10001`. (optional)
expand = '' # str | Use [expand](#expansion) include additional information in the response. This parameter accepts `issueTypeScreenSchemes` that, for each screen schemes, returns information about the issue type screen scheme the screen scheme is assigned to. (optional)
query_string = '' # str | String used to perform a case-insensitive partial match with screen scheme name. (optional)
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `id` Sorts by screen scheme ID.  *  `name` Sorts by screen scheme name. (optional)

try:
    # Get screen schemes
    api_response = api_instance.get_screen_schemes(start_at=start_at, max_results=max_results, id=id, expand=expand, query_string=query_string, order_by=order_by)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenSchemesApi->get_screen_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 25]
 **id** | [**list[int]**](int.md)| The list of screen scheme IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **expand** | **str**| Use [expand](#expansion) include additional information in the response. This parameter accepts &#x60;issueTypeScreenSchemes&#x60; that, for each screen schemes, returns information about the issue type screen scheme the screen scheme is assigned to. | [optional] 
 **query_string** | **str**| String used to perform a case-insensitive partial match with screen scheme name. | [optional] 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;id&#x60; Sorts by screen scheme ID.  *  &#x60;name&#x60; Sorts by screen scheme name. | [optional] 

### Return type

[**PageBeanScreenScheme**](PageBeanScreenScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_screen_scheme**
> object update_screen_scheme(body, screen_scheme_id)

Update screen scheme

Updates a screen scheme. Only screen schemes used in classic projects can be updated.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenSchemesApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateScreenSchemeDetails() # UpdateScreenSchemeDetails | The screen scheme update details.
screen_scheme_id = 'screen_scheme_id_example' # str | The ID of the screen scheme.

try:
    # Update screen scheme
    api_response = api_instance.update_screen_scheme(body, screen_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenSchemesApi->update_screen_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateScreenSchemeDetails**](UpdateScreenSchemeDetails.md)| The screen scheme update details. | 
 **screen_scheme_id** | **str**| The ID of the screen scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

