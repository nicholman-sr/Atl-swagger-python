# jira_client.UIModificationsAppsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_ui_modification**](UIModificationsAppsApi.md#create_ui_modification) | **POST** /rest/api/3/uiModifications | Create UI modification
[**delete_ui_modification**](UIModificationsAppsApi.md#delete_ui_modification) | **DELETE** /rest/api/3/uiModifications/{uiModificationId} | Delete UI modification
[**get_ui_modifications**](UIModificationsAppsApi.md#get_ui_modifications) | **GET** /rest/api/3/uiModifications | Get UI modifications
[**update_ui_modification**](UIModificationsAppsApi.md#update_ui_modification) | **PUT** /rest/api/3/uiModifications/{uiModificationId} | Update UI modification

# **create_ui_modification**
> UiModificationIdentifiers create_ui_modification(body)

Create UI modification

Creates a UI modification. UI modification can only be created by Forge apps.  Each app can define up to 3000 UI modifications. Each UI modification can define up to 1000 contexts. The same context can be assigned to maximum 100 UI modifications.  **[Permissions](#permissions) required:**   *  *None* if the UI modification is created without contexts.  *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for one or more projects, if the UI modification is created with contexts.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.UIModificationsAppsApi(jira_client.ApiClient(configuration))
body = jira_client.CreateUiModificationDetails() # CreateUiModificationDetails | Details of the UI modification.

try:
    # Create UI modification
    api_response = api_instance.create_ui_modification(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UIModificationsAppsApi->create_ui_modification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CreateUiModificationDetails**](CreateUiModificationDetails.md)| Details of the UI modification. | 

### Return type

[**UiModificationIdentifiers**](UiModificationIdentifiers.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_ui_modification**
> object delete_ui_modification(ui_modification_id)

Delete UI modification

Deletes a UI modification. All the contexts that belong to the UI modification are deleted too. UI modification can only be deleted by Forge apps.  **[Permissions](#permissions) required:** None.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.UIModificationsAppsApi(jira_client.ApiClient(configuration))
ui_modification_id = 'ui_modification_id_example' # str | The ID of the UI modification.

try:
    # Delete UI modification
    api_response = api_instance.delete_ui_modification(ui_modification_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UIModificationsAppsApi->delete_ui_modification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **ui_modification_id** | **str**| The ID of the UI modification. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_ui_modifications**
> PageBeanUiModificationDetails get_ui_modifications(start_at=start_at, max_results=max_results, expand=expand)

Get UI modifications

Gets UI modifications. UI modifications can only be retrieved by Forge apps.  **[Permissions](#permissions) required:** None.  The new `read:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.UIModificationsAppsApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
expand = 'expand_example' # str | Use expand to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  `data` Returns UI modification data.  *  `contexts` Returns UI modification contexts. (optional)

try:
    # Get UI modifications
    api_response = api_instance.get_ui_modifications(start_at=start_at, max_results=max_results, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UIModificationsAppsApi->get_ui_modifications: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **expand** | **str**| Use expand to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;data&#x60; Returns UI modification data.  *  &#x60;contexts&#x60; Returns UI modification contexts. | [optional] 

### Return type

[**PageBeanUiModificationDetails**](PageBeanUiModificationDetails.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_ui_modification**
> object update_ui_modification(body, ui_modification_id)

Update UI modification

Updates a UI modification. UI modification can only be updated by Forge apps.  Each UI modification can define up to 1000 contexts. The same context can be assigned to maximum 100 UI modifications.  **[Permissions](#permissions) required:**   *  *None* if the UI modification is created without contexts.  *  *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for one or more projects, if the UI modification is created with contexts.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.UIModificationsAppsApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateUiModificationDetails() # UpdateUiModificationDetails | Details of the UI modification.
ui_modification_id = 'ui_modification_id_example' # str | The ID of the UI modification.

try:
    # Update UI modification
    api_response = api_instance.update_ui_modification(body, ui_modification_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UIModificationsAppsApi->update_ui_modification: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateUiModificationDetails**](UpdateUiModificationDetails.md)| Details of the UI modification. | 
 **ui_modification_id** | **str**| The ID of the UI modification. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

