# jira_client.IssueLinkTypesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_issue_link_type**](IssueLinkTypesApi.md#create_issue_link_type) | **POST** /rest/api/3/issueLinkType | Create issue link type
[**delete_issue_link_type**](IssueLinkTypesApi.md#delete_issue_link_type) | **DELETE** /rest/api/3/issueLinkType/{issueLinkTypeId} | Delete issue link type
[**get_issue_link_type**](IssueLinkTypesApi.md#get_issue_link_type) | **GET** /rest/api/3/issueLinkType/{issueLinkTypeId} | Get issue link type
[**get_issue_link_types**](IssueLinkTypesApi.md#get_issue_link_types) | **GET** /rest/api/3/issueLinkType | Get issue link types
[**update_issue_link_type**](IssueLinkTypesApi.md#update_issue_link_type) | **PUT** /rest/api/3/issueLinkType/{issueLinkTypeId} | Update issue link type

# **create_issue_link_type**
> IssueLinkType create_issue_link_type(body)

Create issue link type

Creates an issue link type. Use this operation to create descriptions of the reasons why issues are linked. The issue link type consists of a name and descriptions for a link's inward and outward relationships.  To use this operation, the site must have [issue linking](https://confluence.atlassian.com/x/yoXKM) enabled.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueLinkTypesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueLinkType() # IssueLinkType | 

try:
    # Create issue link type
    api_response = api_instance.create_issue_link_type(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueLinkTypesApi->create_issue_link_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueLinkType**](IssueLinkType.md)|  | 

### Return type

[**IssueLinkType**](IssueLinkType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_issue_link_type**
> delete_issue_link_type(issue_link_type_id)

Delete issue link type

Deletes an issue link type.  To use this operation, the site must have [issue linking](https://confluence.atlassian.com/x/yoXKM) enabled.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueLinkTypesApi(jira_client.ApiClient(configuration))
issue_link_type_id = 'issue_link_type_id_example' # str | The ID of the issue link type.

try:
    # Delete issue link type
    api_instance.delete_issue_link_type(issue_link_type_id)
except ApiException as e:
    print("Exception when calling IssueLinkTypesApi->delete_issue_link_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_link_type_id** | **str**| The ID of the issue link type. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_link_type**
> IssueLinkType get_issue_link_type(issue_link_type_id)

Get issue link type

Returns an issue link type.  To use this operation, the site must have [issue linking](https://confluence.atlassian.com/x/yoXKM) enabled.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for a project in the site.

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
api_instance = jira_client.IssueLinkTypesApi(jira_client.ApiClient(configuration))
issue_link_type_id = 'issue_link_type_id_example' # str | The ID of the issue link type.

try:
    # Get issue link type
    api_response = api_instance.get_issue_link_type(issue_link_type_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueLinkTypesApi->get_issue_link_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **issue_link_type_id** | **str**| The ID of the issue link type. | 

### Return type

[**IssueLinkType**](IssueLinkType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_issue_link_types**
> IssueLinkTypes get_issue_link_types()

Get issue link types

Returns a list of all issue link types.  To use this operation, the site must have [issue linking](https://confluence.atlassian.com/x/yoXKM) enabled.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for a project in the site.

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
api_instance = jira_client.IssueLinkTypesApi(jira_client.ApiClient(configuration))

try:
    # Get issue link types
    api_response = api_instance.get_issue_link_types()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueLinkTypesApi->get_issue_link_types: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**IssueLinkTypes**](IssueLinkTypes.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_issue_link_type**
> IssueLinkType update_issue_link_type(body, issue_link_type_id)

Update issue link type

Updates an issue link type.  To use this operation, the site must have [issue linking](https://confluence.atlassian.com/x/yoXKM) enabled.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueLinkTypesApi(jira_client.ApiClient(configuration))
body = jira_client.IssueLinkType() # IssueLinkType | 
issue_link_type_id = 'issue_link_type_id_example' # str | The ID of the issue link type.

try:
    # Update issue link type
    api_response = api_instance.update_issue_link_type(body, issue_link_type_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueLinkTypesApi->update_issue_link_type: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**IssueLinkType**](IssueLinkType.md)|  | 
 **issue_link_type_id** | **str**| The ID of the issue link type. | 

### Return type

[**IssueLinkType**](IssueLinkType.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

