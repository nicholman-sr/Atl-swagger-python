# jira_client.IssueSecuritySchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_security_level**](IssueSecuritySchemesApi.md#add_security_level) | **PUT** /rest/api/3/issuesecurityschemes/{schemeId}/level | Add issue security levels
[**add_security_level_members**](IssueSecuritySchemesApi.md#add_security_level_members) | **PUT** /rest/api/3/issuesecurityschemes/{schemeId}/level/{levelId}/member | Add issue security level members
[**associate_schemes_to_projects**](IssueSecuritySchemesApi.md#associate_schemes_to_projects) | **PUT** /rest/api/3/issuesecurityschemes/project | Associate security scheme to project
[**create_issue_security_scheme**](IssueSecuritySchemesApi.md#create_issue_security_scheme) | **POST** /rest/api/3/issuesecurityschemes | Create issue security scheme
[**delete_security_scheme**](IssueSecuritySchemesApi.md#delete_security_scheme) | **DELETE** /rest/api/3/issuesecurityschemes/{schemeId} | Delete issue security scheme
[**get_issue_security_scheme**](IssueSecuritySchemesApi.md#get_issue_security_scheme) | **GET** /rest/api/3/issuesecurityschemes/{id} | Get issue security scheme
[**get_issue_security_schemes**](IssueSecuritySchemesApi.md#get_issue_security_schemes) | **GET** /rest/api/3/issuesecurityschemes | Get issue security schemes
[**get_security_level_members**](IssueSecuritySchemesApi.md#get_security_level_members) | **GET** /rest/api/3/issuesecurityschemes/level/member | Get issue security level members
[**get_security_levels**](IssueSecuritySchemesApi.md#get_security_levels) | **GET** /rest/api/3/issuesecurityschemes/level | Get issue security levels
[**remove_level**](IssueSecuritySchemesApi.md#remove_level) | **DELETE** /rest/api/3/issuesecurityschemes/{schemeId}/level/{levelId} | Remove issue security level
[**remove_member_from_security_level**](IssueSecuritySchemesApi.md#remove_member_from_security_level) | **DELETE** /rest/api/3/issuesecurityschemes/{schemeId}/level/{levelId}/member/{memberId} | Remove member from issue security level
[**search_projects_using_security_schemes**](IssueSecuritySchemesApi.md#search_projects_using_security_schemes) | **GET** /rest/api/3/issuesecurityschemes/project | Get projects using issue security schemes
[**search_security_schemes**](IssueSecuritySchemesApi.md#search_security_schemes) | **GET** /rest/api/3/issuesecurityschemes/search | Search issue security schemes
[**set_default_levels**](IssueSecuritySchemesApi.md#set_default_levels) | **PUT** /rest/api/3/issuesecurityschemes/level/default | Set default issue security levels
[**update_issue_security_scheme**](IssueSecuritySchemesApi.md#update_issue_security_scheme) | **PUT** /rest/api/3/issuesecurityschemes/{id} | Update issue security scheme
[**update_security_level**](IssueSecuritySchemesApi.md#update_security_level) | **PUT** /rest/api/3/issuesecurityschemes/{schemeId}/level/{levelId} | Update issue security level

# **add_security_level**
> object add_security_level(body, scheme_id)

Add issue security levels

Adds levels and levels' members to the issue security scheme. You can add up to 100 levels per request.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.AddSecuritySchemeLevelsRequestBean() # AddSecuritySchemeLevelsRequestBean | 
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme.

try:
    # Add issue security levels
    api_response = api_instance.add_security_level(body, scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->add_security_level: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AddSecuritySchemeLevelsRequestBean**](AddSecuritySchemeLevelsRequestBean.md)|  | 
 **scheme_id** | **str**| The ID of the issue security scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_security_level_members**
> object add_security_level_members(body, scheme_id, level_id)

Add issue security level members

Adds members to the issue security level. You can add up to 100 members per request.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.SecuritySchemeMembersRequest() # SecuritySchemeMembersRequest | 
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme.
level_id = 'level_id_example' # str | The ID of the issue security level.

try:
    # Add issue security level members
    api_response = api_instance.add_security_level_members(body, scheme_id, level_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->add_security_level_members: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SecuritySchemeMembersRequest**](SecuritySchemeMembersRequest.md)|  | 
 **scheme_id** | **str**| The ID of the issue security scheme. | 
 **level_id** | **str**| The ID of the issue security level. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **associate_schemes_to_projects**
> associate_schemes_to_projects(body)

Associate security scheme to project

Associates an issue security scheme with a project and remaps security levels of issues to the new levels, if provided.  This operation is [asynchronous](#async). Follow the `location` link in the response to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain subsequent updates.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.AssociateSecuritySchemeWithProjectDetails() # AssociateSecuritySchemeWithProjectDetails | 

try:
    # Associate security scheme to project
    api_instance.associate_schemes_to_projects(body)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->associate_schemes_to_projects: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AssociateSecuritySchemeWithProjectDetails**](AssociateSecuritySchemeWithProjectDetails.md)|  | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_issue_security_scheme**
> SecuritySchemeId create_issue_security_scheme(body)

Create issue security scheme

Creates a security scheme with security scheme levels and levels' members. You can create up to 100 security scheme levels and security scheme levels' members per request.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "Newly created issue security scheme",
  "levels" : [ {
    "description" : "Newly created level",
    "isDefault" : true,
    "members" : [ {
      "parameter" : "administrators",
      "type" : "group"
    } ],
    "name" : "New level"
  } ],
  "name" : "New security scheme"
} # dict(str, object) | 

try:
    # Create issue security scheme
    api_response = api_instance.create_issue_security_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->create_issue_security_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

[**SecuritySchemeId**](SecuritySchemeId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_security_scheme**
> object delete_security_scheme(scheme_id)

Delete issue security scheme

Deletes an issue security scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme.

try:
    # Delete issue security scheme
    api_response = api_instance.delete_security_scheme(scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->delete_security_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The ID of the issue security scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_security_scheme**
> SecurityScheme get_issue_security_scheme(id)

Get issue security scheme

Returns an issue security scheme along with its security levels.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  *Administer Projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for a project that uses the requested issue security scheme.

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the issue security scheme. Use the [Get issue security schemes](#api-rest-api-3-issuesecurityschemes-get) operation to get a list of issue security scheme IDs.

try:
    # Get issue security scheme
    api_response = api_instance.get_issue_security_scheme(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->get_issue_security_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the issue security scheme. Use the [Get issue security schemes](#api-rest-api-3-issuesecurityschemes-get) operation to get a list of issue security scheme IDs. | 

### Return type

[**SecurityScheme**](SecurityScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_security_schemes**
> SecuritySchemes get_issue_security_schemes()

Get issue security schemes

Returns all [issue security schemes](https://confluence.atlassian.com/x/J4lKLg).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))

try:
    # Get issue security schemes
    api_response = api_instance.get_issue_security_schemes()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->get_issue_security_schemes: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**SecuritySchemes**](SecuritySchemes.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_security_level_members**
> PageBeanSecurityLevelMember get_security_level_members(start_at=start_at, max_results=max_results, id=id, scheme_id=scheme_id, level_id=level_id, expand=expand)

Get issue security level members

Returns a [paginated](#pagination) list of issue security level members.  Only issue security level members in the context of classic projects are returned.  Filtering using parameters is inclusive: if you specify both security scheme IDs and level IDs, the result will include all issue security level members from the specified schemes and levels.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of issue security level member IDs. To include multiple issue security level members separate IDs with an ampersand: `id=10000&id=10001`. (optional)
scheme_id = ['scheme_id_example'] # list[str] | The list of issue security scheme IDs. To include multiple issue security schemes separate IDs with an ampersand: `schemeId=10000&schemeId=10001`. (optional)
level_id = ['level_id_example'] # list[str] | The list of issue security level IDs. To include multiple issue security levels separate IDs with an ampersand: `levelId=10000&levelId=10001`. (optional)
expand = 'expand_example' # str | Use expand to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  `all` Returns all expandable information  *  `field` Returns information about the custom field granted the permission  *  `group` Returns information about the group that is granted the permission  *  `projectRole` Returns information about the project role granted the permission  *  `user` Returns information about the user who is granted the permission (optional)

try:
    # Get issue security level members
    api_response = api_instance.get_security_level_members(start_at=start_at, max_results=max_results, id=id, scheme_id=scheme_id, level_id=level_id, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->get_security_level_members: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of issue security level member IDs. To include multiple issue security level members separate IDs with an ampersand: &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **scheme_id** | [**list[str]**](str.md)| The list of issue security scheme IDs. To include multiple issue security schemes separate IDs with an ampersand: &#x60;schemeId&#x3D;10000&amp;schemeId&#x3D;10001&#x60;. | [optional] 
 **level_id** | [**list[str]**](str.md)| The list of issue security level IDs. To include multiple issue security levels separate IDs with an ampersand: &#x60;levelId&#x3D;10000&amp;levelId&#x3D;10001&#x60;. | [optional] 
 **expand** | **str**| Use expand to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;all&#x60; Returns all expandable information  *  &#x60;field&#x60; Returns information about the custom field granted the permission  *  &#x60;group&#x60; Returns information about the group that is granted the permission  *  &#x60;projectRole&#x60; Returns information about the project role granted the permission  *  &#x60;user&#x60; Returns information about the user who is granted the permission | [optional] 

### Return type

[**PageBeanSecurityLevelMember**](PageBeanSecurityLevelMember.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_security_levels**
> PageBeanSecurityLevel get_security_levels(start_at=start_at, max_results=max_results, id=id, scheme_id=scheme_id, only_default=only_default)

Get issue security levels

Returns a [paginated](#pagination) list of issue security levels.  Only issue security levels in the context of classic projects are returned.  Filtering using IDs is inclusive: if you specify both security scheme IDs and level IDs, the result will include both specified issue security levels and all issue security levels from the specified schemes.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of issue security scheme level IDs. To include multiple issue security levels, separate IDs with an ampersand: `id=10000&id=10001`. (optional)
scheme_id = ['scheme_id_example'] # list[str] | The list of issue security scheme IDs. To include multiple issue security schemes, separate IDs with an ampersand: `schemeId=10000&schemeId=10001`. (optional)
only_default = false # bool | When set to true, returns multiple default levels for each security scheme containing a default. If you provide scheme and level IDs not associated with the default, returns an empty page. The default value is false. (optional) (default to false)

try:
    # Get issue security levels
    api_response = api_instance.get_security_levels(start_at=start_at, max_results=max_results, id=id, scheme_id=scheme_id, only_default=only_default)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->get_security_levels: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of issue security scheme level IDs. To include multiple issue security levels, separate IDs with an ampersand: &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **scheme_id** | [**list[str]**](str.md)| The list of issue security scheme IDs. To include multiple issue security schemes, separate IDs with an ampersand: &#x60;schemeId&#x3D;10000&amp;schemeId&#x3D;10001&#x60;. | [optional] 
 **only_default** | **bool**| When set to true, returns multiple default levels for each security scheme containing a default. If you provide scheme and level IDs not associated with the default, returns an empty page. The default value is false. | [optional] [default to false]

### Return type

[**PageBeanSecurityLevel**](PageBeanSecurityLevel.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_level**
> remove_level(scheme_id, level_id, replace_with=replace_with)

Remove issue security level

Deletes an issue security level.  This operation is [asynchronous](#async). Follow the `location` link in the response to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain subsequent updates.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme.
level_id = 'level_id_example' # str | The ID of the issue security level to remove.
replace_with = 'replace_with_example' # str | The ID of the issue security level that will replace the currently selected level. (optional)

try:
    # Remove issue security level
    api_instance.remove_level(scheme_id, level_id, replace_with=replace_with)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->remove_level: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The ID of the issue security scheme. | 
 **level_id** | **str**| The ID of the issue security level to remove. | 
 **replace_with** | **str**| The ID of the issue security level that will replace the currently selected level. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_member_from_security_level**
> object remove_member_from_security_level(scheme_id, level_id, member_id)

Remove member from issue security level

Removes an issue security level member from an issue security scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme.
level_id = 'level_id_example' # str | The ID of the issue security level.
member_id = 'member_id_example' # str | The ID of the issue security level member to be removed.

try:
    # Remove member from issue security level
    api_response = api_instance.remove_member_from_security_level(scheme_id, level_id, member_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->remove_member_from_security_level: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **scheme_id** | **str**| The ID of the issue security scheme. | 
 **level_id** | **str**| The ID of the issue security level. | 
 **member_id** | **str**| The ID of the issue security level member to be removed. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_projects_using_security_schemes**
> PageBeanIssueSecuritySchemeToProjectMapping search_projects_using_security_schemes(start_at=start_at, max_results=max_results, issue_security_scheme_id=issue_security_scheme_id, project_id=project_id)

Get projects using issue security schemes

Returns a [paginated](#pagination) mapping of projects that are using security schemes. You can provide either one or multiple security scheme IDs or project IDs to filter by. If you don't provide any, this will return a list of all mappings. Only issue security schemes in the context of classic projects are supported. **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
issue_security_scheme_id = ['issue_security_scheme_id_example'] # list[str] | The list of security scheme IDs to be filtered out. (optional)
project_id = ['project_id_example'] # list[str] | The list of project IDs to be filtered out. (optional)

try:
    # Get projects using issue security schemes
    api_response = api_instance.search_projects_using_security_schemes(start_at=start_at, max_results=max_results, issue_security_scheme_id=issue_security_scheme_id, project_id=project_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->search_projects_using_security_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **issue_security_scheme_id** | [**list[str]**](str.md)| The list of security scheme IDs to be filtered out. | [optional] 
 **project_id** | [**list[str]**](str.md)| The list of project IDs to be filtered out. | [optional] 

### Return type

[**PageBeanIssueSecuritySchemeToProjectMapping**](PageBeanIssueSecuritySchemeToProjectMapping.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_security_schemes**
> PageBeanSecuritySchemeWithProjects search_security_schemes(start_at=start_at, max_results=max_results, id=id, project_id=project_id)

Search issue security schemes

Returns a [paginated](#pagination) list of issue security schemes.   If you specify the project ID parameter, the result will contain issue security schemes and related project IDs you filter by. Use \\{@link IssueSecuritySchemeResource\\#searchProjectsUsingSecuritySchemes(String, String, Set, Set)\\} to obtain all projects related to scheme.  Only issue security schemes in the context of classic projects are returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of issue security scheme IDs. To include multiple issue security scheme IDs, separate IDs with an ampersand: `id=10000&id=10001`. (optional)
project_id = ['project_id_example'] # list[str] | The list of project IDs. To include multiple project IDs, separate IDs with an ampersand: `projectId=10000&projectId=10001`. (optional)

try:
    # Search issue security schemes
    api_response = api_instance.search_security_schemes(start_at=start_at, max_results=max_results, id=id, project_id=project_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->search_security_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of issue security scheme IDs. To include multiple issue security scheme IDs, separate IDs with an ampersand: &#x60;id&#x3D;10000&amp;id&#x3D;10001&#x60;. | [optional] 
 **project_id** | [**list[str]**](str.md)| The list of project IDs. To include multiple project IDs, separate IDs with an ampersand: &#x60;projectId&#x3D;10000&amp;projectId&#x3D;10001&#x60;. | [optional] 

### Return type

[**PageBeanSecuritySchemeWithProjects**](PageBeanSecuritySchemeWithProjects.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_default_levels**
> object set_default_levels(body)

Set default issue security levels

Sets default issue security levels for schemes.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = {
  "defaultValues" : [ {
    "defaultLevelId" : "20000",
    "issueSecuritySchemeId" : "10000"
  }, {
    "defaultLevelId" : "30000",
    "issueSecuritySchemeId" : "12000"
  } ]
} # dict(str, object) | 

try:
    # Set default issue security levels
    api_response = api_instance.set_default_levels(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->set_default_levels: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_issue_security_scheme**
> object update_issue_security_scheme(body, id)

Update issue security scheme

Updates the issue security scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = jira_client.UpdateIssueSecuritySchemeRequestBean() # UpdateIssueSecuritySchemeRequestBean | 
id = 'id_example' # str | The ID of the issue security scheme.

try:
    # Update issue security scheme
    api_response = api_instance.update_issue_security_scheme(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->update_issue_security_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**UpdateIssueSecuritySchemeRequestBean**](UpdateIssueSecuritySchemeRequestBean.md)|  | 
 **id** | **str**| The ID of the issue security scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_security_level**
> object update_security_level(body, scheme_id, level_id)

Update issue security level

Updates the issue security level.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueSecuritySchemesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "New level description",
  "name" : "New level name"
} # dict(str, object) | 
scheme_id = 'scheme_id_example' # str | The ID of the issue security scheme level belongs to.
level_id = 'level_id_example' # str | The ID of the issue security level to update.

try:
    # Update issue security level
    api_response = api_instance.update_security_level(body, scheme_id, level_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueSecuritySchemesApi->update_security_level: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **scheme_id** | **str**| The ID of the issue security scheme level belongs to. | 
 **level_id** | **str**| The ID of the issue security level to update. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

