# jira_client.PermissionsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_all_permissions**](PermissionsApi.md#get_all_permissions) | **GET** /rest/api/3/permissions | Get all permissions
[**get_bulk_permissions**](PermissionsApi.md#get_bulk_permissions) | **POST** /rest/api/3/permissions/check | Get bulk permissions
[**get_my_permissions**](PermissionsApi.md#get_my_permissions) | **GET** /rest/api/3/mypermissions | Get my permissions
[**get_permitted_projects**](PermissionsApi.md#get_permitted_projects) | **POST** /rest/api/3/permissions/project | Get permitted projects

# **get_all_permissions**
> Permissions get_all_permissions()

Get all permissions

Returns all permissions, including:   *  global permissions.  *  project permissions.  *  global permissions added by plugins.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.PermissionsApi(jira_client.ApiClient(configuration))

try:
    # Get all permissions
    api_response = api_instance.get_all_permissions()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PermissionsApi->get_all_permissions: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**Permissions**](Permissions.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_bulk_permissions**
> BulkPermissionGrants get_bulk_permissions(body)

Get bulk permissions

Returns:   *  for a list of global permissions, the global permissions granted to a user.  *  for a list of project permissions and lists of projects and issues, for each project permission a list of the projects and issues a user can access or manipulate.  If no account ID is provided, the operation returns details for the logged in user.  Note that:   *  Invalid project and issue IDs are ignored.  *  A maximum of 1000 projects and 1000 issues can be checked.  *  Null values in `globalPermissions`, `projectPermissions`, `projectPermissions.projects`, and `projectPermissions.issues` are ignored.  *  Empty strings in `projectPermissions.permissions` are ignored.  **Deprecation notice:** The required OAuth 2.0 scopes will be updated on June 15, 2024.   *  **Classic**: `read:jira-work`  *  **Granular**: `read:permission:jira`  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg) to check the permissions for other users, otherwise none. However, Connect apps can make a call from the app server to the product to obtain permission details for any user, without admin permission. This Connect app ability doesn't apply to calls made using AP.request() in a browser.

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
api_instance = jira_client.PermissionsApi(jira_client.ApiClient(configuration))
body = jira_client.BulkPermissionsRequestBean() # BulkPermissionsRequestBean | Details of the permissions to check.

try:
    # Get bulk permissions
    api_response = api_instance.get_bulk_permissions(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PermissionsApi->get_bulk_permissions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkPermissionsRequestBean**](BulkPermissionsRequestBean.md)| Details of the permissions to check. | 

### Return type

[**BulkPermissionGrants**](BulkPermissionGrants.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_my_permissions**
> Permissions get_my_permissions(project_key=project_key, project_id=project_id, issue_key=issue_key, issue_id=issue_id, permissions=permissions, project_uuid=project_uuid, project_configuration_uuid=project_configuration_uuid, comment_id=comment_id)

Get my permissions

Returns a list of permissions indicating which permissions the user has. Details of the user's permissions can be obtained in a global, project, issue or comment context.  The user is reported as having a project permission:   *  in the global context, if the user has the project permission in any project.  *  for a project, where the project permission is determined using issue data, if the user meets the permission's criteria for any issue in the project. Otherwise, if the user has the project permission in the project.  *  for an issue, where a project permission is determined using issue data, if the user has the permission in the issue. Otherwise, if the user has the project permission in the project containing the issue.  *  for a comment, where the user has both the permission to browse the comment and the project permission for the comment's parent issue. Only the BROWSE\\_PROJECTS permission is supported. If a `commentId` is provided whose `permissions` does not equal BROWSE\\_PROJECTS, a 400 error will be returned.  This means that users may be shown as having an issue permission (such as EDIT\\_ISSUES) in the global context or a project context but may not have the permission for any or all issues. For example, if Reporters have the EDIT\\_ISSUES permission a user would be shown as having this permission in the global context or the context of a project, because any user can be a reporter. However, if they are not the user who reported the issue queried they would not have EDIT\\_ISSUES permission for that issue.  For [Jira Service Management project permissions](https://support.atlassian.com/jira-cloud-administration/docs/customize-jira-service-management-permissions/), this will be evaluated similarly to a user in the customer portal. For example, if the BROWSE\\_PROJECTS permission is granted to Service Project Customer - Portal Access, any users with access to the customer portal will have the BROWSE\\_PROJECTS permission.  Global permissions are unaffected by context.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.PermissionsApi(jira_client.ApiClient(configuration))
project_key = 'project_key_example' # str | The key of project. Ignored if `projectId` is provided. (optional)
project_id = 'project_id_example' # str | The ID of project. (optional)
issue_key = 'issue_key_example' # str | The key of the issue. Ignored if `issueId` is provided. (optional)
issue_id = 'issue_id_example' # str | The ID of the issue. (optional)
permissions = 'permissions_example' # str | A list of permission keys. (Required) This parameter accepts a comma-separated list. To get the list of available permissions, use [Get all permissions](#api-rest-api-3-permissions-get). (optional)
project_uuid = 'project_uuid_example' # str |  (optional)
project_configuration_uuid = 'project_configuration_uuid_example' # str |  (optional)
comment_id = 'comment_id_example' # str | The ID of the comment. (optional)

try:
    # Get my permissions
    api_response = api_instance.get_my_permissions(project_key=project_key, project_id=project_id, issue_key=issue_key, issue_id=issue_id, permissions=permissions, project_uuid=project_uuid, project_configuration_uuid=project_configuration_uuid, comment_id=comment_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PermissionsApi->get_my_permissions: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_key** | **str**| The key of project. Ignored if &#x60;projectId&#x60; is provided. | [optional] 
 **project_id** | **str**| The ID of project. | [optional] 
 **issue_key** | **str**| The key of the issue. Ignored if &#x60;issueId&#x60; is provided. | [optional] 
 **issue_id** | **str**| The ID of the issue. | [optional] 
 **permissions** | **str**| A list of permission keys. (Required) This parameter accepts a comma-separated list. To get the list of available permissions, use [Get all permissions](#api-rest-api-3-permissions-get). | [optional] 
 **project_uuid** | **str**|  | [optional] 
 **project_configuration_uuid** | **str**|  | [optional] 
 **comment_id** | **str**| The ID of the comment. | [optional] 

### Return type

[**Permissions**](Permissions.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_permitted_projects**
> PermittedProjects get_permitted_projects(body)

Get permitted projects

Returns all the projects where the user is granted a list of project permissions.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.PermissionsApi(jira_client.ApiClient(configuration))
body = jira_client.PermissionsKeysBean() # PermissionsKeysBean | 

try:
    # Get permitted projects
    api_response = api_instance.get_permitted_projects(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling PermissionsApi->get_permitted_projects: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**PermissionsKeysBean**](PermissionsKeysBean.md)|  | 

### Return type

[**PermittedProjects**](PermittedProjects.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

