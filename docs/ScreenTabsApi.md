# jira_client.ScreenTabsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_screen_tab**](ScreenTabsApi.md#add_screen_tab) | **POST** /rest/api/3/screens/{screenId}/tabs | Create screen tab
[**delete_screen_tab**](ScreenTabsApi.md#delete_screen_tab) | **DELETE** /rest/api/3/screens/{screenId}/tabs/{tabId} | Delete screen tab
[**get_all_screen_tabs**](ScreenTabsApi.md#get_all_screen_tabs) | **GET** /rest/api/3/screens/{screenId}/tabs | Get all screen tabs
[**get_bulk_screen_tabs**](ScreenTabsApi.md#get_bulk_screen_tabs) | **GET** /rest/api/3/screens/tabs | Get bulk screen tabs
[**move_screen_tab**](ScreenTabsApi.md#move_screen_tab) | **POST** /rest/api/3/screens/{screenId}/tabs/{tabId}/move/{pos} | Move screen tab
[**rename_screen_tab**](ScreenTabsApi.md#rename_screen_tab) | **PUT** /rest/api/3/screens/{screenId}/tabs/{tabId} | Update screen tab

# **add_screen_tab**
> ScreenableTab add_screen_tab(body, screen_id)

Create screen tab

Creates a tab for a screen.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
body = jira_client.ScreenableTab() # ScreenableTab | 
screen_id = 789 # int | The ID of the screen.

try:
    # Create screen tab
    api_response = api_instance.add_screen_tab(body, screen_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->add_screen_tab: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ScreenableTab**](ScreenableTab.md)|  | 
 **screen_id** | **int**| The ID of the screen. | 

### Return type

[**ScreenableTab**](ScreenableTab.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_screen_tab**
> delete_screen_tab(screen_id, tab_id)

Delete screen tab

Deletes a screen tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.

try:
    # Delete screen tab
    api_instance.delete_screen_tab(screen_id, tab_id)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->delete_screen_tab: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_screen_tabs**
> list[ScreenableTab] get_all_screen_tabs(screen_id, project_key=project_key)

Get all screen tabs

Returns the list of tabs for a screen.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) when the project key is specified, providing that the screen is associated with the project through a Screen Scheme and Issue Type Screen Scheme.

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.
project_key = 'project_key_example' # str | The key of the project. (optional)

try:
    # Get all screen tabs
    api_response = api_instance.get_all_screen_tabs(screen_id, project_key=project_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->get_all_screen_tabs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 
 **project_key** | **str**| The key of the project. | [optional] 

### Return type

[**list[ScreenableTab]**](ScreenableTab.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_bulk_screen_tabs**
> get_bulk_screen_tabs(screen_id=screen_id, tab_id=tab_id, start_at=start_at, max_result=max_result)

Get bulk screen tabs

Returns the list of tabs for a bulk of screens.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
screen_id = [56] # list[int] | The list of screen IDs. To include multiple screen IDs, provide an ampersand-separated list. For example, `screenId=10000&screenId=10001`. (optional)
tab_id = [56] # list[int] | The list of tab IDs. To include multiple tab IDs, provide an ampersand-separated list. For example, `tabId=10000&tabId=10001`. (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_result = 100 # int | The maximum number of items to return per page. The maximum number is 100, (optional) (default to 100)

try:
    # Get bulk screen tabs
    api_instance.get_bulk_screen_tabs(screen_id=screen_id, tab_id=tab_id, start_at=start_at, max_result=max_result)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->get_bulk_screen_tabs: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | [**list[int]**](int.md)| The list of screen IDs. To include multiple screen IDs, provide an ampersand-separated list. For example, &#x60;screenId&#x3D;10000&amp;screenId&#x3D;10001&#x60;. | [optional] 
 **tab_id** | [**list[int]**](int.md)| The list of tab IDs. To include multiple tab IDs, provide an ampersand-separated list. For example, &#x60;tabId&#x3D;10000&amp;tabId&#x3D;10001&#x60;. | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_result** | **int**| The maximum number of items to return per page. The maximum number is 100, | [optional] [default to 100]

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_screen_tab**
> object move_screen_tab(screen_id, tab_id, pos)

Move screen tab

Moves a screen tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.
pos = 56 # int | The position of tab. The base index is 0.

try:
    # Move screen tab
    api_response = api_instance.move_screen_tab(screen_id, tab_id, pos)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->move_screen_tab: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 
 **pos** | **int**| The position of tab. The base index is 0. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **rename_screen_tab**
> ScreenableTab rename_screen_tab(body, screen_id, tab_id)

Update screen tab

Updates the name of a screen tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabsApi(jira_client.ApiClient(configuration))
body = jira_client.ScreenableTab() # ScreenableTab | 
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.

try:
    # Update screen tab
    api_response = api_instance.rename_screen_tab(body, screen_id, tab_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabsApi->rename_screen_tab: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ScreenableTab**](ScreenableTab.md)|  | 
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 

### Return type

[**ScreenableTab**](ScreenableTab.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

