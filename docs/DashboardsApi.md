# jira_client.DashboardsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_gadget**](DashboardsApi.md#add_gadget) | **POST** /rest/api/3/dashboard/{dashboardId}/gadget | Add gadget to dashboard
[**bulk_edit_dashboards**](DashboardsApi.md#bulk_edit_dashboards) | **PUT** /rest/api/3/dashboard/bulk/edit | Bulk edit dashboards
[**copy_dashboard**](DashboardsApi.md#copy_dashboard) | **POST** /rest/api/3/dashboard/{id}/copy | Copy dashboard
[**create_dashboard**](DashboardsApi.md#create_dashboard) | **POST** /rest/api/3/dashboard | Create dashboard
[**delete_dashboard**](DashboardsApi.md#delete_dashboard) | **DELETE** /rest/api/3/dashboard/{id} | Delete dashboard
[**delete_dashboard_item_property**](DashboardsApi.md#delete_dashboard_item_property) | **DELETE** /rest/api/3/dashboard/{dashboardId}/items/{itemId}/properties/{propertyKey} | Delete dashboard item property
[**get_all_available_dashboard_gadgets**](DashboardsApi.md#get_all_available_dashboard_gadgets) | **GET** /rest/api/3/dashboard/gadgets | Get available gadgets
[**get_all_dashboards**](DashboardsApi.md#get_all_dashboards) | **GET** /rest/api/3/dashboard | Get all dashboards
[**get_all_gadgets**](DashboardsApi.md#get_all_gadgets) | **GET** /rest/api/3/dashboard/{dashboardId}/gadget | Get gadgets
[**get_dashboard**](DashboardsApi.md#get_dashboard) | **GET** /rest/api/3/dashboard/{id} | Get dashboard
[**get_dashboard_item_property**](DashboardsApi.md#get_dashboard_item_property) | **GET** /rest/api/3/dashboard/{dashboardId}/items/{itemId}/properties/{propertyKey} | Get dashboard item property
[**get_dashboard_item_property_keys**](DashboardsApi.md#get_dashboard_item_property_keys) | **GET** /rest/api/3/dashboard/{dashboardId}/items/{itemId}/properties | Get dashboard item property keys
[**get_dashboards_paginated**](DashboardsApi.md#get_dashboards_paginated) | **GET** /rest/api/3/dashboard/search | Search for dashboards
[**remove_gadget**](DashboardsApi.md#remove_gadget) | **DELETE** /rest/api/3/dashboard/{dashboardId}/gadget/{gadgetId} | Remove gadget from dashboard
[**set_dashboard_item_property**](DashboardsApi.md#set_dashboard_item_property) | **PUT** /rest/api/3/dashboard/{dashboardId}/items/{itemId}/properties/{propertyKey} | Set dashboard item property
[**update_dashboard**](DashboardsApi.md#update_dashboard) | **PUT** /rest/api/3/dashboard/{id} | Update dashboard
[**update_gadget**](DashboardsApi.md#update_gadget) | **PUT** /rest/api/3/dashboard/{dashboardId}/gadget/{gadgetId} | Update gadget on dashboard

# **add_gadget**
> DashboardGadget add_gadget(body, dashboard_id)

Add gadget to dashboard

Adds a gadget to a dashboard.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.DashboardGadgetSettings() # DashboardGadgetSettings | 
dashboard_id = 789 # int | The ID of the dashboard.

try:
    # Add gadget to dashboard
    api_response = api_instance.add_gadget(body, dashboard_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->add_gadget: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DashboardGadgetSettings**](DashboardGadgetSettings.md)|  | 
 **dashboard_id** | **int**| The ID of the dashboard. | 

### Return type

[**DashboardGadget**](DashboardGadget.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **bulk_edit_dashboards**
> BulkEditShareableEntityResponse bulk_edit_dashboards(body)

Bulk edit dashboards

Bulk edit dashboards. Maximum number of dashboards to be edited at the same time is 100.  **[Permissions](#permissions) required:** None  The dashboards to be updated must be owned by the user, or the user must be an administrator.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.BulkEditShareableEntityRequest() # BulkEditShareableEntityRequest | The details of dashboards being updated in bulk.

try:
    # Bulk edit dashboards
    api_response = api_instance.bulk_edit_dashboards(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->bulk_edit_dashboards: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkEditShareableEntityRequest**](BulkEditShareableEntityRequest.md)| The details of dashboards being updated in bulk. | 

### Return type

[**BulkEditShareableEntityResponse**](BulkEditShareableEntityResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **copy_dashboard**
> Dashboard copy_dashboard(body, id, extend_admin_permissions=extend_admin_permissions)

Copy dashboard

Copies a dashboard. Any values provided in the `dashboard` parameter replace those in the copied dashboard.  **[Permissions](#permissions) required:** None  The dashboard to be copied must be owned by or shared with the user.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.DashboardDetails() # DashboardDetails | Dashboard details.
id = 'id_example' # str | 
extend_admin_permissions = false # bool | Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) (optional) (default to false)

try:
    # Copy dashboard
    api_response = api_instance.copy_dashboard(body, id, extend_admin_permissions=extend_admin_permissions)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->copy_dashboard: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DashboardDetails**](DashboardDetails.md)| Dashboard details. | 
 **id** | **str**|  | 
 **extend_admin_permissions** | **bool**| Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) | [optional] [default to false]

### Return type

[**Dashboard**](Dashboard.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_dashboard**
> Dashboard create_dashboard(body, extend_admin_permissions=extend_admin_permissions)

Create dashboard

Creates a dashboard.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.DashboardDetails() # DashboardDetails | Dashboard details.
extend_admin_permissions = false # bool | Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) (optional) (default to false)

try:
    # Create dashboard
    api_response = api_instance.create_dashboard(body, extend_admin_permissions=extend_admin_permissions)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->create_dashboard: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DashboardDetails**](DashboardDetails.md)| Dashboard details. | 
 **extend_admin_permissions** | **bool**| Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) | [optional] [default to false]

### Return type

[**Dashboard**](Dashboard.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_dashboard**
> delete_dashboard(id)

Delete dashboard

Deletes a dashboard.  **[Permissions](#permissions) required:** None  The dashboard to be deleted must be owned by the user.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the dashboard.

try:
    # Delete dashboard
    api_instance.delete_dashboard(id)
except ApiException as e:
    print("Exception when calling DashboardsApi->delete_dashboard: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the dashboard. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_dashboard_item_property**
> object delete_dashboard_item_property(dashboard_id, item_id, property_key)

Delete dashboard item property

Deletes a dashboard item property.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The user must be the owner of the dashboard. Note, users with the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) are considered owners of the System dashboard.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_id = 'dashboard_id_example' # str | The ID of the dashboard.
item_id = 'item_id_example' # str | The ID of the dashboard item.
property_key = 'property_key_example' # str | The key of the dashboard item property.

try:
    # Delete dashboard item property
    api_response = api_instance.delete_dashboard_item_property(dashboard_id, item_id, property_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->delete_dashboard_item_property: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_id** | **str**| The ID of the dashboard. | 
 **item_id** | **str**| The ID of the dashboard item. | 
 **property_key** | **str**| The key of the dashboard item property. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_available_dashboard_gadgets**
> AvailableDashboardGadgetsResponse get_all_available_dashboard_gadgets()

Get available gadgets

Gets a list of all available gadgets that can be added to all dashboards.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))

try:
    # Get available gadgets
    api_response = api_instance.get_all_available_dashboard_gadgets()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_all_available_dashboard_gadgets: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**AvailableDashboardGadgetsResponse**](AvailableDashboardGadgetsResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_dashboards**
> PageOfDashboards get_all_dashboards(filter=filter, start_at=start_at, max_results=max_results)

Get all dashboards

Returns a list of dashboards owned by or shared with the user. The list may be filtered to include only favorite or owned dashboards.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
filter = 'filter_example' # str | The filter applied to the list of dashboards. Valid values are:   *  `favourite` Returns dashboards the user has marked as favorite.  *  `my` Returns dashboards owned by the user. (optional)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 20 # int | The maximum number of items to return per page. (optional) (default to 20)

try:
    # Get all dashboards
    api_response = api_instance.get_all_dashboards(filter=filter, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_all_dashboards: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **filter** | **str**| The filter applied to the list of dashboards. Valid values are:   *  &#x60;favourite&#x60; Returns dashboards the user has marked as favorite.  *  &#x60;my&#x60; Returns dashboards owned by the user. | [optional] 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 20]

### Return type

[**PageOfDashboards**](PageOfDashboards.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_all_gadgets**
> DashboardGadgetResponse get_all_gadgets(dashboard_id, module_key=module_key, uri=uri, gadget_id=gadget_id)

Get gadgets

Returns a list of dashboard gadgets on a dashboard.  This operation returns:   *  Gadgets from a list of IDs, when `id` is set.  *  Gadgets with a module key, when `moduleKey` is set.  *  Gadgets from a list of URIs, when `uri` is set.  *  All gadgets, when no other parameters are set.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_id = 789 # int | The ID of the dashboard.
module_key = ['module_key_example'] # list[str] | The list of gadgets module keys. To include multiple module keys, separate module keys with ampersand: `moduleKey=key:one&moduleKey=key:two`. (optional)
uri = ['uri_example'] # list[str] | The list of gadgets URIs. To include multiple URIs, separate URIs with ampersand: `uri=/rest/example/uri/1&uri=/rest/example/uri/2`. (optional)
gadget_id = [56] # list[int] | The list of gadgets IDs. To include multiple IDs, separate IDs with ampersand: `gadgetId=10000&gadgetId=10001`. (optional)

try:
    # Get gadgets
    api_response = api_instance.get_all_gadgets(dashboard_id, module_key=module_key, uri=uri, gadget_id=gadget_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_all_gadgets: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_id** | **int**| The ID of the dashboard. | 
 **module_key** | [**list[str]**](str.md)| The list of gadgets module keys. To include multiple module keys, separate module keys with ampersand: &#x60;moduleKey&#x3D;key:one&amp;moduleKey&#x3D;key:two&#x60;. | [optional] 
 **uri** | [**list[str]**](str.md)| The list of gadgets URIs. To include multiple URIs, separate URIs with ampersand: &#x60;uri&#x3D;/rest/example/uri/1&amp;uri&#x3D;/rest/example/uri/2&#x60;. | [optional] 
 **gadget_id** | [**list[int]**](int.md)| The list of gadgets IDs. To include multiple IDs, separate IDs with ampersand: &#x60;gadgetId&#x3D;10000&amp;gadgetId&#x3D;10001&#x60;. | [optional] 

### Return type

[**DashboardGadgetResponse**](DashboardGadgetResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dashboard**
> Dashboard get_dashboard(id)

Get dashboard

Returns a dashboard.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.  However, to get a dashboard, the dashboard must be shared with the user or the user must own it. Note, users with the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) are considered owners of the System dashboard. The System dashboard is considered to be shared with all other users.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the dashboard.

try:
    # Get dashboard
    api_response = api_instance.get_dashboard(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_dashboard: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the dashboard. | 

### Return type

[**Dashboard**](Dashboard.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dashboard_item_property**
> EntityProperty get_dashboard_item_property(dashboard_id, item_id, property_key)

Get dashboard item property

Returns the key and value of a dashboard item property.  A dashboard item enables an app to add user-specific information to a user dashboard. Dashboard items are exposed to users as gadgets that users can add to their dashboards. For more information on how users do this, see [Adding and customizing gadgets](https://confluence.atlassian.com/x/7AeiLQ).  When an app creates a dashboard item it registers a callback to receive the dashboard item ID. The callback fires whenever the item is rendered or, where the item is configurable, the user edits the item. The app then uses this resource to store the item's content or configuration details. For more information on working with dashboard items, see [ Building a dashboard item for a JIRA Connect add-on](https://developer.atlassian.com/server/jira/platform/guide-building-a-dashboard-item-for-a-jira-connect-add-on-33746254/) and the [Dashboard Item](https://developer.atlassian.com/cloud/jira/platform/modules/dashboard-item/) documentation.  There is no resource to set or get dashboard items.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The user must be the owner of the dashboard or have the dashboard shared with them. Note, users with the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) are considered owners of the System dashboard. The System dashboard is considered to be shared with all other users, and is accessible to anonymous users when Jira\\\\u2019s anonymous access is permitted.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_id = 'dashboard_id_example' # str | The ID of the dashboard.
item_id = 'item_id_example' # str | The ID of the dashboard item.
property_key = 'property_key_example' # str | The key of the dashboard item property.

try:
    # Get dashboard item property
    api_response = api_instance.get_dashboard_item_property(dashboard_id, item_id, property_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_dashboard_item_property: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_id** | **str**| The ID of the dashboard. | 
 **item_id** | **str**| The ID of the dashboard item. | 
 **property_key** | **str**| The key of the dashboard item property. | 

### Return type

[**EntityProperty**](EntityProperty.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dashboard_item_property_keys**
> PropertyKeys get_dashboard_item_property_keys(dashboard_id, item_id)

Get dashboard item property keys

Returns the keys of all properties for a dashboard item.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The user must be the owner of the dashboard or have the dashboard shared with them. Note, users with the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) are considered owners of the System dashboard. The System dashboard is considered to be shared with all other users, and is accessible to anonymous users when Jira\\\\u2019s anonymous access is permitted.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_id = 'dashboard_id_example' # str | The ID of the dashboard.
item_id = 'item_id_example' # str | The ID of the dashboard item.

try:
    # Get dashboard item property keys
    api_response = api_instance.get_dashboard_item_property_keys(dashboard_id, item_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_dashboard_item_property_keys: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_id** | **str**| The ID of the dashboard. | 
 **item_id** | **str**| The ID of the dashboard item. | 

### Return type

[**PropertyKeys**](PropertyKeys.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dashboards_paginated**
> PageBeanDashboard get_dashboards_paginated(dashboard_name=dashboard_name, account_id=account_id, owner=owner, groupname=groupname, group_id=group_id, project_id=project_id, order_by=order_by, start_at=start_at, max_results=max_results, status=status, expand=expand)

Search for dashboards

Returns a [paginated](#pagination) list of dashboards. This operation is similar to [Get dashboards](#api-rest-api-3-dashboard-get) except that the results can be refined to include dashboards that have specific attributes. For example, dashboards with a particular name. When multiple attributes are specified only filters matching all attributes are returned.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The following dashboards that match the query parameters are returned:   *  Dashboards owned by the user. Not returned for anonymous users.  *  Dashboards shared with a group that the user is a member of. Not returned for anonymous users.  *  Dashboards shared with a private project that the user can browse. Not returned for anonymous users.  *  Dashboards shared with a public project.  *  Dashboards shared with the public.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_name = 'dashboard_name_example' # str | String used to perform a case-insensitive partial match with `name`. (optional)
account_id = 'account_id_example' # str | User account ID used to return dashboards with the matching `owner.accountId`. This parameter cannot be used with the `owner` parameter. (optional)
owner = 'owner_example' # str | This parameter is deprecated because of privacy changes. Use `accountId` instead. See the [migration guide](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. User name used to return dashboards with the matching `owner.name`. This parameter cannot be used with the `accountId` parameter. (optional)
groupname = 'groupname_example' # str | As a group's name can change, use of `groupId` is recommended. Group name used to return dashboards that are shared with a group that matches `sharePermissions.group.name`. This parameter cannot be used with the `groupId` parameter. (optional)
group_id = 'group_id_example' # str | Group ID used to return dashboards that are shared with a group that matches `sharePermissions.group.groupId`. This parameter cannot be used with the `groupname` parameter. (optional)
project_id = 789 # int | Project ID used to returns dashboards that are shared with a project that matches `sharePermissions.project.id`. (optional)
order_by = 'name' # str | [Order](#ordering) the results by a field:   *  `description` Sorts by dashboard description. Note that this sort works independently of whether the expand to display the description field is in use.  *  `favourite_count` Sorts by dashboard popularity.  *  `id` Sorts by dashboard ID.  *  `is_favourite` Sorts by whether the dashboard is marked as a favorite.  *  `name` Sorts by dashboard name.  *  `owner` Sorts by dashboard owner name. (optional) (default to name)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 50 # int | The maximum number of items to return per page. (optional) (default to 50)
status = 'active' # str | The status to filter by. It may be active, archived or deleted. (optional) (default to active)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information about dashboard in the response. This parameter accepts a comma-separated list. Expand options include:   *  `description` Returns the description of the dashboard.  *  `owner` Returns the owner of the dashboard.  *  `viewUrl` Returns the URL that is used to view the dashboard.  *  `favourite` Returns `isFavourite`, an indicator of whether the user has set the dashboard as a favorite.  *  `favouritedCount` Returns `popularity`, a count of how many users have set this dashboard as a favorite.  *  `sharePermissions` Returns details of the share permissions defined for the dashboard.  *  `editPermissions` Returns details of the edit permissions defined for the dashboard.  *  `isWritable` Returns whether the current user has permission to edit the dashboard. (optional)

try:
    # Search for dashboards
    api_response = api_instance.get_dashboards_paginated(dashboard_name=dashboard_name, account_id=account_id, owner=owner, groupname=groupname, group_id=group_id, project_id=project_id, order_by=order_by, start_at=start_at, max_results=max_results, status=status, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->get_dashboards_paginated: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_name** | **str**| String used to perform a case-insensitive partial match with &#x60;name&#x60;. | [optional] 
 **account_id** | **str**| User account ID used to return dashboards with the matching &#x60;owner.accountId&#x60;. This parameter cannot be used with the &#x60;owner&#x60; parameter. | [optional] 
 **owner** | **str**| This parameter is deprecated because of privacy changes. Use &#x60;accountId&#x60; instead. See the [migration guide](https://developer.atlassian.com/cloud/jira/platform/deprecation-notice-user-privacy-api-migration-guide/) for details. User name used to return dashboards with the matching &#x60;owner.name&#x60;. This parameter cannot be used with the &#x60;accountId&#x60; parameter. | [optional] 
 **groupname** | **str**| As a group&#x27;s name can change, use of &#x60;groupId&#x60; is recommended. Group name used to return dashboards that are shared with a group that matches &#x60;sharePermissions.group.name&#x60;. This parameter cannot be used with the &#x60;groupId&#x60; parameter. | [optional] 
 **group_id** | **str**| Group ID used to return dashboards that are shared with a group that matches &#x60;sharePermissions.group.groupId&#x60;. This parameter cannot be used with the &#x60;groupname&#x60; parameter. | [optional] 
 **project_id** | **int**| Project ID used to returns dashboards that are shared with a project that matches &#x60;sharePermissions.project.id&#x60;. | [optional] 
 **order_by** | **str**| [Order](#ordering) the results by a field:   *  &#x60;description&#x60; Sorts by dashboard description. Note that this sort works independently of whether the expand to display the description field is in use.  *  &#x60;favourite_count&#x60; Sorts by dashboard popularity.  *  &#x60;id&#x60; Sorts by dashboard ID.  *  &#x60;is_favourite&#x60; Sorts by whether the dashboard is marked as a favorite.  *  &#x60;name&#x60; Sorts by dashboard name.  *  &#x60;owner&#x60; Sorts by dashboard owner name. | [optional] [default to name]
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 50]
 **status** | **str**| The status to filter by. It may be active, archived or deleted. | [optional] [default to active]
 **expand** | **str**| Use [expand](#expansion) to include additional information about dashboard in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;description&#x60; Returns the description of the dashboard.  *  &#x60;owner&#x60; Returns the owner of the dashboard.  *  &#x60;viewUrl&#x60; Returns the URL that is used to view the dashboard.  *  &#x60;favourite&#x60; Returns &#x60;isFavourite&#x60;, an indicator of whether the user has set the dashboard as a favorite.  *  &#x60;favouritedCount&#x60; Returns &#x60;popularity&#x60;, a count of how many users have set this dashboard as a favorite.  *  &#x60;sharePermissions&#x60; Returns details of the share permissions defined for the dashboard.  *  &#x60;editPermissions&#x60; Returns details of the edit permissions defined for the dashboard.  *  &#x60;isWritable&#x60; Returns whether the current user has permission to edit the dashboard. | [optional] 

### Return type

[**PageBeanDashboard**](PageBeanDashboard.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_gadget**
> object remove_gadget(dashboard_id, gadget_id)

Remove gadget from dashboard

Removes a dashboard gadget from a dashboard.  When a gadget is removed from a dashboard, other gadgets in the same column are moved up to fill the emptied position.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
dashboard_id = 789 # int | The ID of the dashboard.
gadget_id = 789 # int | The ID of the gadget.

try:
    # Remove gadget from dashboard
    api_response = api_instance.remove_gadget(dashboard_id, gadget_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->remove_gadget: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **dashboard_id** | **int**| The ID of the dashboard. | 
 **gadget_id** | **int**| The ID of the gadget. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_dashboard_item_property**
> object set_dashboard_item_property(body, dashboard_id, item_id, property_key)

Set dashboard item property

Sets the value of a dashboard item property. Use this resource in apps to store custom data against a dashboard item.  A dashboard item enables an app to add user-specific information to a user dashboard. Dashboard items are exposed to users as gadgets that users can add to their dashboards. For more information on how users do this, see [Adding and customizing gadgets](https://confluence.atlassian.com/x/7AeiLQ).  When an app creates a dashboard item it registers a callback to receive the dashboard item ID. The callback fires whenever the item is rendered or, where the item is configurable, the user edits the item. The app then uses this resource to store the item's content or configuration details. For more information on working with dashboard items, see [ Building a dashboard item for a JIRA Connect add-on](https://developer.atlassian.com/server/jira/platform/guide-building-a-dashboard-item-for-a-jira-connect-add-on-33746254/) and the [Dashboard Item](https://developer.atlassian.com/cloud/jira/platform/modules/dashboard-item/) documentation.  There is no resource to set or get dashboard items.  The value of the request body must be a [valid](http://tools.ietf.org/html/rfc4627), non-empty JSON blob. The maximum length is 32768 characters.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The user must be the owner of the dashboard. Note, users with the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) are considered owners of the System dashboard.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = {
  "number" : 5,
  "string" : "string-value"
} # object | The value of the property. The value has to be a valid, non-empty [JSON](https://tools.ietf.org/html/rfc4627) value. The maximum length of the property value is 32768 bytes.
dashboard_id = 'dashboard_id_example' # str | The ID of the dashboard.
item_id = 'item_id_example' # str | The ID of the dashboard item.
property_key = 'property_key_example' # str | The key of the dashboard item property. The maximum length is 255 characters. For dashboard items with a spec URI and no complete module key, if the provided propertyKey is equal to \"config\", the request body's JSON must be an object with all keys and values as strings.

try:
    # Set dashboard item property
    api_response = api_instance.set_dashboard_item_property(body, dashboard_id, item_id, property_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->set_dashboard_item_property: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)| The value of the property. The value has to be a valid, non-empty [JSON](https://tools.ietf.org/html/rfc4627) value. The maximum length of the property value is 32768 bytes. | 
 **dashboard_id** | **str**| The ID of the dashboard. | 
 **item_id** | **str**| The ID of the dashboard item. | 
 **property_key** | **str**| The key of the dashboard item property. The maximum length is 255 characters. For dashboard items with a spec URI and no complete module key, if the provided propertyKey is equal to \&quot;config\&quot;, the request body&#x27;s JSON must be an object with all keys and values as strings. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_dashboard**
> Dashboard update_dashboard(body, id, extend_admin_permissions=extend_admin_permissions)

Update dashboard

Updates a dashboard, replacing all the dashboard details with those provided.  **[Permissions](#permissions) required:** None  The dashboard to be updated must be owned by the user.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.DashboardDetails() # DashboardDetails | Replacement dashboard details.
id = 'id_example' # str | The ID of the dashboard to update.
extend_admin_permissions = false # bool | Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) (optional) (default to false)

try:
    # Update dashboard
    api_response = api_instance.update_dashboard(body, id, extend_admin_permissions=extend_admin_permissions)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->update_dashboard: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DashboardDetails**](DashboardDetails.md)| Replacement dashboard details. | 
 **id** | **str**| The ID of the dashboard to update. | 
 **extend_admin_permissions** | **bool**| Whether admin level permissions are used. It should only be true if the user has *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) | [optional] [default to false]

### Return type

[**Dashboard**](Dashboard.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_gadget**
> object update_gadget(body, dashboard_id, gadget_id)

Update gadget on dashboard

Changes the title, position, and color of the gadget on a dashboard.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.DashboardsApi(jira_client.ApiClient(configuration))
body = jira_client.DashboardGadgetUpdateRequest() # DashboardGadgetUpdateRequest | 
dashboard_id = 789 # int | The ID of the dashboard.
gadget_id = 789 # int | The ID of the gadget.

try:
    # Update gadget on dashboard
    api_response = api_instance.update_gadget(body, dashboard_id, gadget_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DashboardsApi->update_gadget: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DashboardGadgetUpdateRequest**](DashboardGadgetUpdateRequest.md)|  | 
 **dashboard_id** | **int**| The ID of the dashboard. | 
 **gadget_id** | **int**| The ID of the gadget. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

