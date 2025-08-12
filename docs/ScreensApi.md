# jira_client.ScreensApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_field_to_default_screen**](ScreensApi.md#add_field_to_default_screen) | **POST** /rest/api/3/screens/addToDefault/{fieldId} | Add field to default screen
[**create_screen**](ScreensApi.md#create_screen) | **POST** /rest/api/3/screens | Create screen
[**delete_screen**](ScreensApi.md#delete_screen) | **DELETE** /rest/api/3/screens/{screenId} | Delete screen
[**get_available_screen_fields**](ScreensApi.md#get_available_screen_fields) | **GET** /rest/api/3/screens/{screenId}/availableFields | Get available screen fields
[**get_screens**](ScreensApi.md#get_screens) | **GET** /rest/api/3/screens | Get screens
[**get_screens_for_field**](ScreensApi.md#get_screens_for_field) | **GET** /rest/api/3/field/{fieldId}/screens | Get screens for a field
[**update_screen**](ScreensApi.md#update_screen) | **PUT** /rest/api/3/screens/{screenId} | Update screen

# **add_field_to_default_screen**
> object add_field_to_default_screen(field_id)

Add field to default screen

Adds a field to the default tab of the default screen.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
field_id = 'field_id_example' # str | The ID of the field.

try:
    # Add field to default screen
    api_response = api_instance.add_field_to_default_screen(field_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->add_field_to_default_screen: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **field_id** | **str**| The ID of the field. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_screen**
> Screen create_screen(body)

Create screen

Creates a screen with a default field tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
body = jira_client.ScreenDetails() # ScreenDetails | 

try:
    # Create screen
    api_response = api_instance.create_screen(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->create_screen: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ScreenDetails**](ScreenDetails.md)|  | 

### Return type

[**Screen**](Screen.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_screen**
> delete_screen(screen_id)

Delete screen

Deletes a screen. A screen cannot be deleted if it is used in a screen scheme, workflow, or workflow draft.  Only screens used in classic projects can be deleted.

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.

try:
    # Delete screen
    api_instance.delete_screen(screen_id)
except ApiException as e:
    print("Exception when calling ScreensApi->delete_screen: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_available_screen_fields**
> list[ScreenableField] get_available_screen_fields(screen_id)

Get available screen fields

Returns the fields that can be added to a tab on a screen.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.

try:
    # Get available screen fields
    api_response = api_instance.get_available_screen_fields(screen_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->get_available_screen_fields: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 

### Return type

[**list[ScreenableField]**](ScreenableField.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screens**
> PageBeanScreen get_screens(start_at=start_at, max_results=max_results, id=id, query_string=query_string, scope=scope, order_by=order_by)

Get screens

Returns a [paginated](#pagination) list of all screens or those specified by one or more screen IDs.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)
id = [56] # list[int] | The list of screen IDs. To include multiple IDs, provide an ampersand-separated list. For example, `id=10000&id=10001`. (optional)
query_string = '' # str | String used to perform a case-insensitive partial match with screen name. (optional)
scope = ['scope_example'] # list[str] | The scope filter string. To filter by multiple scope, provide an ampersand-separated list. For example, `scope=GLOBAL&scope=PROJECT`. (optional)
order_by = 'order_by_example' # str | [Order](#ordering) the results by a field:   *  `id` Sorts by screen ID.  *  `name` Sorts by screen name. (optional)

try:
    # Get screens
    api_response = api_instance.get_screens(start_at=start_at, max_results=max_results, id=id, query_string=query_string, scope=scope, order_by=order_by)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->get_screens: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]
 **id** | [**list[int]**](int.md)| The list of screen IDs. To include multiple IDs, provide an ampersand-separated list. For example, &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **query_string** | **str**| String used to perform a case-insensitive partial match with screen name. | [optional] 
 **scope** | [**list[str]**](str.md)| The scope filter string. To filter by multiple scope, provide an ampersand-separated list. For example, &#x60;scope&#x3D;GLOBAL&amp;scope&#x3D;PROJECT&#x60;. | [optional] 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;id&#x60; Sorts by screen ID.  *  &#x60;name&#x60; Sorts by screen name. | [optional] 

### Return type

[**PageBeanScreen**](PageBeanScreen.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_screens_for_field**
> PageBeanScreenWithTab get_screens_for_field(field_id, start_at=start_at, max_results=max_results, expand=expand)

Get screens for a field

Returns a [paginated](#pagination) list of the screens a field is used in.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
field_id = 'field_id_example' # str | The ID of the field to return screens for.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about screens in the response. This parameter accepts `tab` which returns details about the screen tabs the field is used in. (optional)

try:
    # Get screens for a field
    api_response = api_instance.get_screens_for_field(field_id, start_at=start_at, max_results=max_results, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->get_screens_for_field: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **field_id** | **str**| The ID of the field to return screens for. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]
 **expand** | **str**| Use [expand](#expansion) to include additional information about screens in the response. This parameter accepts &#x60;tab&#x60; which returns details about the screen tabs the field is used in. | [optional] 

### Return type

[**PageBeanScreenWithTab**](PageBeanScreenWithTab.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_screen**
> Screen update_screen(body, screen_id)

Update screen

Updates a screen. Only screens used in classic projects can be updated.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreensApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateScreenDetails() # UpdateScreenDetails | 
screen_id = 789 # int | The ID of the screen.

try:
    # Update screen
    api_response = api_instance.update_screen(body, screen_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreensApi->update_screen: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateScreenDetails**](UpdateScreenDetails.md)|  | 
 **screen_id** | **int**| The ID of the screen. | 

### Return type

[**Screen**](Screen.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

