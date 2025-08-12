# jira_client.FilterSharingApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_share_permission**](FilterSharingApi.md#add_share_permission) | **POST** /rest/api/3/filter/{id}/permission | Add share permission
[**delete_share_permission**](FilterSharingApi.md#delete_share_permission) | **DELETE** /rest/api/3/filter/{id}/permission/{permissionId} | Delete share permission
[**get_default_share_scope**](FilterSharingApi.md#get_default_share_scope) | **GET** /rest/api/3/filter/defaultShareScope | Get default share scope
[**get_share_permission**](FilterSharingApi.md#get_share_permission) | **GET** /rest/api/3/filter/{id}/permission/{permissionId} | Get share permission
[**get_share_permissions**](FilterSharingApi.md#get_share_permissions) | **GET** /rest/api/3/filter/{id}/permission | Get share permissions
[**set_default_share_scope**](FilterSharingApi.md#set_default_share_scope) | **PUT** /rest/api/3/filter/defaultShareScope | Set default share scope

# **add_share_permission**
> list[SharePermission] add_share_permission(body, id)

Add share permission

Add a share permissions to a filter. If you add a global share permission (one for all logged-in users or the public) it will overwrite all share permissions for the filter.  Be aware that this operation uses different objects for updating share permissions compared to [Update filter](#api-rest-api-3-filter-id-put).  **[Permissions](#permissions) required:** *Share dashboards and filters* [global permission](https://confluence.atlassian.com/x/x4dKLg) and the user must own the filter.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))
body = jira_client.SharePermissionInputBean() # SharePermissionInputBean | 
id = 789 # int | The ID of the filter.

try:
    # Add share permission
    api_response = api_instance.add_share_permission(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling FilterSharingApi->add_share_permission: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SharePermissionInputBean**](SharePermissionInputBean.md)|  | 
 **id** | **int**| The ID of the filter. | 

### Return type

[**list[SharePermission]**](SharePermission.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_share_permission**
> delete_share_permission(id, permission_id)

Delete share permission

Deletes a share permission from a filter.  **[Permissions](#permissions) required:** Permission to access Jira and the user must own the filter.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the filter.
permission_id = 789 # int | The ID of the share permission.

try:
    # Delete share permission
    api_instance.delete_share_permission(id, permission_id)
except ApiException as e:
    print("Exception when calling FilterSharingApi->delete_share_permission: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the filter. | 
 **permission_id** | **int**| The ID of the share permission. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_default_share_scope**
> DefaultShareScope get_default_share_scope()

Get default share scope

Returns the default sharing settings for new filters and dashboards for a user.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))

try:
    # Get default share scope
    api_response = api_instance.get_default_share_scope()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling FilterSharingApi->get_default_share_scope: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**DefaultShareScope**](DefaultShareScope.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_share_permission**
> SharePermission get_share_permission(id, permission_id)

Get share permission

Returns a share permission for a filter. A filter can be shared with groups, projects, all logged-in users, or the public. Sharing with all logged-in users or the public is known as a global share permission.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None, however, a share permission is only returned for:   *  filters owned by the user.  *  filters shared with a group that the user is a member of.  *  filters shared with a private project that the user has *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for.  *  filters shared with a public project.  *  filters shared with the public.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the filter.
permission_id = 789 # int | The ID of the share permission.

try:
    # Get share permission
    api_response = api_instance.get_share_permission(id, permission_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling FilterSharingApi->get_share_permission: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the filter. | 
 **permission_id** | **int**| The ID of the share permission. | 

### Return type

[**SharePermission**](SharePermission.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_share_permissions**
> list[SharePermission] get_share_permissions(id)

Get share permissions

Returns the share permissions for a filter. A filter can be shared with groups, projects, all logged-in users, or the public. Sharing with all logged-in users or the public is known as a global share permission.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None, however, share permissions are only returned for:   *  filters owned by the user.  *  filters shared with a group that the user is a member of.  *  filters shared with a private project that the user has *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for.  *  filters shared with a public project.  *  filters shared with the public.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the filter.

try:
    # Get share permissions
    api_response = api_instance.get_share_permissions(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling FilterSharingApi->get_share_permissions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the filter. | 

### Return type

[**list[SharePermission]**](SharePermission.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_default_share_scope**
> DefaultShareScope set_default_share_scope(body)

Set default share scope

Sets the default sharing for new filters and dashboards for a user.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.FilterSharingApi(jira_client.ApiClient(configuration))
body = jira_client.DefaultShareScope() # DefaultShareScope | 

try:
    # Set default share scope
    api_response = api_instance.set_default_share_scope(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling FilterSharingApi->set_default_share_scope: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**DefaultShareScope**](DefaultShareScope.md)|  | 

### Return type

[**DefaultShareScope**](DefaultShareScope.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

