# jira_client.ScreenTabFieldsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_screen_tab_field**](ScreenTabFieldsApi.md#add_screen_tab_field) | **POST** /rest/api/3/screens/{screenId}/tabs/{tabId}/fields | Add screen tab field
[**get_all_screen_tab_fields**](ScreenTabFieldsApi.md#get_all_screen_tab_fields) | **GET** /rest/api/3/screens/{screenId}/tabs/{tabId}/fields | Get all screen tab fields
[**move_screen_tab_field**](ScreenTabFieldsApi.md#move_screen_tab_field) | **POST** /rest/api/3/screens/{screenId}/tabs/{tabId}/fields/{id}/move | Move screen tab field
[**remove_screen_tab_field**](ScreenTabFieldsApi.md#remove_screen_tab_field) | **DELETE** /rest/api/3/screens/{screenId}/tabs/{tabId}/fields/{id} | Remove screen tab field

# **add_screen_tab_field**
> ScreenableField add_screen_tab_field(body, screen_id, tab_id)

Add screen tab field

Adds a field to a screen tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabFieldsApi(jira_client.ApiClient(configuration))
body = jira_client.AddFieldBean() # AddFieldBean | 
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.

try:
    # Add screen tab field
    api_response = api_instance.add_screen_tab_field(body, screen_id, tab_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabFieldsApi->add_screen_tab_field: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AddFieldBean**](AddFieldBean.md)|  | 
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 

### Return type

[**ScreenableField**](ScreenableField.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_screen_tab_fields**
> list[ScreenableField] get_all_screen_tab_fields(screen_id, tab_id, project_key=project_key)

Get all screen tab fields

Returns all fields for a screen tab.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  *Administer projects* [project permission](https://confluence.atlassian.com/x/yodKLg) when the project key is specified, providing that the screen is associated with the project through a Screen Scheme and Issue Type Screen Scheme.

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
api_instance = jira_client.ScreenTabFieldsApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.
project_key = 'project_key_example' # str | The key of the project. (optional)

try:
    # Get all screen tab fields
    api_response = api_instance.get_all_screen_tab_fields(screen_id, tab_id, project_key=project_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabFieldsApi->get_all_screen_tab_fields: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 
 **project_key** | **str**| The key of the project. | [optional] 

### Return type

[**list[ScreenableField]**](ScreenableField.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_screen_tab_field**
> object move_screen_tab_field(body, screen_id, tab_id, id)

Move screen tab field

Moves a screen tab field.  If `after` and `position` are provided in the request, `position` is ignored.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabFieldsApi(jira_client.ApiClient(configuration))
body = jira_client.MoveFieldBean() # MoveFieldBean | 
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.
id = 'id_example' # str | The ID of the field.

try:
    # Move screen tab field
    api_response = api_instance.move_screen_tab_field(body, screen_id, tab_id, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ScreenTabFieldsApi->move_screen_tab_field: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**MoveFieldBean**](MoveFieldBean.md)|  | 
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 
 **id** | **str**| The ID of the field. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_screen_tab_field**
> remove_screen_tab_field(screen_id, tab_id, id)

Remove screen tab field

Removes a field from a screen tab.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.ScreenTabFieldsApi(jira_client.ApiClient(configuration))
screen_id = 789 # int | The ID of the screen.
tab_id = 789 # int | The ID of the screen tab.
id = 'id_example' # str | The ID of the field.

try:
    # Remove screen tab field
    api_instance.remove_screen_tab_field(screen_id, tab_id, id)
except ApiException as e:
    print("Exception when calling ScreenTabFieldsApi->remove_screen_tab_field: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **screen_id** | **int**| The ID of the screen. | 
 **tab_id** | **int**| The ID of the screen tab. | 
 **id** | **str**| The ID of the field. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

