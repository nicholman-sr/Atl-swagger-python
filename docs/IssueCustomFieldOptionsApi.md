# jira_client.IssueCustomFieldOptionsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_custom_field_option**](IssueCustomFieldOptionsApi.md#create_custom_field_option) | **POST** /rest/api/3/field/{fieldId}/context/{contextId}/option | Create custom field options (context)
[**delete_custom_field_option**](IssueCustomFieldOptionsApi.md#delete_custom_field_option) | **DELETE** /rest/api/3/field/{fieldId}/context/{contextId}/option/{optionId} | Delete custom field options (context)
[**get_custom_field_option**](IssueCustomFieldOptionsApi.md#get_custom_field_option) | **GET** /rest/api/3/customFieldOption/{id} | Get custom field option
[**get_options_for_context**](IssueCustomFieldOptionsApi.md#get_options_for_context) | **GET** /rest/api/3/field/{fieldId}/context/{contextId}/option | Get custom field options (context)
[**reorder_custom_field_options**](IssueCustomFieldOptionsApi.md#reorder_custom_field_options) | **PUT** /rest/api/3/field/{fieldId}/context/{contextId}/option/move | Reorder custom field options (context)
[**replace_custom_field_option**](IssueCustomFieldOptionsApi.md#replace_custom_field_option) | **DELETE** /rest/api/3/field/{fieldId}/context/{contextId}/option/{optionId}/issue | Replace custom field options
[**update_custom_field_option**](IssueCustomFieldOptionsApi.md#update_custom_field_option) | **PUT** /rest/api/3/field/{fieldId}/context/{contextId}/option | Update custom field options (context)

# **create_custom_field_option**
> CustomFieldCreatedContextOptionsList create_custom_field_option(body, field_id, context_id)

Create custom field options (context)

Creates options and, where the custom select field is of the type Select List (cascading), cascading options for a custom select field. The options are added to a context of the field.  The maximum number of options that can be created per request is 1000 and each field can have a maximum of 10000 options.  This operation works for custom field options created in Jira or the operations from this resource. **To work with issue field select list options created for Connect apps use the [Issue custom field options (apps)](#api-group-issue-custom-field-options--apps-) operations.**  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
body = jira_client.BulkCustomFieldOptionCreateRequest() # BulkCustomFieldOptionCreateRequest | 
field_id = 'field_id_example' # str | The ID of the custom field.
context_id = 789 # int | The ID of the context.

try:
    # Create custom field options (context)
    api_response = api_instance.create_custom_field_option(body, field_id, context_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->create_custom_field_option: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkCustomFieldOptionCreateRequest**](BulkCustomFieldOptionCreateRequest.md)|  | 
 **field_id** | **str**| The ID of the custom field. | 
 **context_id** | **int**| The ID of the context. | 

### Return type

[**CustomFieldCreatedContextOptionsList**](CustomFieldCreatedContextOptionsList.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_custom_field_option**
> delete_custom_field_option(field_id, context_id, option_id)

Delete custom field options (context)

Deletes a custom field option.  Options with cascading options cannot be deleted without deleting the cascading options first.  This operation works for custom field options created in Jira or the operations from this resource. **To work with issue field select list options created for Connect apps use the [Issue custom field options (apps)](#api-group-issue-custom-field-options--apps-) operations.**  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
field_id = 'field_id_example' # str | The ID of the custom field.
context_id = 789 # int | The ID of the context from which an option should be deleted.
option_id = 789 # int | The ID of the option to delete.

try:
    # Delete custom field options (context)
    api_instance.delete_custom_field_option(field_id, context_id, option_id)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->delete_custom_field_option: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **field_id** | **str**| The ID of the custom field. | 
 **context_id** | **int**| The ID of the context from which an option should be deleted. | 
 **option_id** | **int**| The ID of the option to delete. | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_custom_field_option**
> CustomFieldOption get_custom_field_option(id)

Get custom field option

Returns a custom field option. For example, an option in a select list.  Note that this operation **only works for issue field select list options created in Jira or using operations from the [Issue custom field options](#api-group-Issue-custom-field-options) resource**, it cannot be used with issue field select list options created by Connect apps.  This operation can be accessed anonymously.  **[Permissions](#permissions) required:** The custom field option is returned as follows:   *  if the user has the *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).  *  if the user has the *Browse projects* [project permission](https://confluence.atlassian.com/x/yodKLg) for at least one project the custom field is used in, and the field is visible in at least one layout the user has permission to view.

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
id = 'id_example' # str | The ID of the custom field option.

try:
    # Get custom field option
    api_response = api_instance.get_custom_field_option(id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->get_custom_field_option: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| The ID of the custom field option. | 

### Return type

[**CustomFieldOption**](CustomFieldOption.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_options_for_context**
> PageBeanCustomFieldContextOption get_options_for_context(field_id, context_id, option_id=option_id, only_options=only_options, start_at=start_at, max_results=max_results)

Get custom field options (context)

Returns a [paginated](#pagination) list of all custom field option for a context. Options are returned first then cascading options, in the order they display in Jira.  This operation works for custom field options created in Jira or the operations from this resource. **To work with issue field select list options created for Connect apps use the [Issue custom field options (apps)](#api-group-issue-custom-field-options--apps-) operations.**  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg). *Edit Workflow* [edit workflow permission](https://support.atlassian.com/jira-cloud-administration/docs/permissions-for-company-managed-projects/#Edit-Workflows)

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
field_id = 'field_id_example' # str | The ID of the custom field.
context_id = 789 # int | The ID of the context.
option_id = 789 # int | The ID of the option. (optional)
only_options = false # bool | Whether only options are returned. (optional) (default to false)
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)

try:
    # Get custom field options (context)
    api_response = api_instance.get_options_for_context(field_id, context_id, option_id=option_id, only_options=only_options, start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->get_options_for_context: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **field_id** | **str**| The ID of the custom field. | 
 **context_id** | **int**| The ID of the context. | 
 **option_id** | **int**| The ID of the option. | [optional] 
 **only_options** | **bool**| Whether only options are returned. | [optional] [default to false]
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]

### Return type

[**PageBeanCustomFieldContextOption**](PageBeanCustomFieldContextOption.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **reorder_custom_field_options**
> object reorder_custom_field_options(body, field_id, context_id)

Reorder custom field options (context)

Changes the order of custom field options or cascading options in a context.  This operation works for custom field options created in Jira or the operations from this resource. **To work with issue field select list options created for Connect apps use the [Issue custom field options (apps)](#api-group-issue-custom-field-options--apps-) operations.**  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
body = jira_client.OrderOfCustomFieldOptions() # OrderOfCustomFieldOptions | 
field_id = 'field_id_example' # str | The ID of the custom field.
context_id = 789 # int | The ID of the context.

try:
    # Reorder custom field options (context)
    api_response = api_instance.reorder_custom_field_options(body, field_id, context_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->reorder_custom_field_options: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**OrderOfCustomFieldOptions**](OrderOfCustomFieldOptions.md)|  | 
 **field_id** | **str**| The ID of the custom field. | 
 **context_id** | **int**| The ID of the context. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **replace_custom_field_option**
> replace_custom_field_option(field_id, option_id, context_id, replace_with=replace_with, jql=jql)

Replace custom field options

Replaces the options of a custom field.  Note that this operation **only works for issue field select list options created in Jira or using operations from the [Issue custom field options](#api-group-Issue-custom-field-options) resource**, it cannot be used with issue field select list options created by Connect or Forge apps.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
field_id = 'field_id_example' # str | The ID of the custom field.
option_id = 789 # int | The ID of the option to be deselected.
context_id = 789 # int | The ID of the context.
replace_with = 789 # int | The ID of the option that will replace the currently selected option. (optional)
jql = 'jql_example' # str | A JQL query that specifies the issues to be updated. For example, *project=10000*. (optional)

try:
    # Replace custom field options
    api_instance.replace_custom_field_option(field_id, option_id, context_id, replace_with=replace_with, jql=jql)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->replace_custom_field_option: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **field_id** | **str**| The ID of the custom field. | 
 **option_id** | **int**| The ID of the option to be deselected. | 
 **context_id** | **int**| The ID of the context. | 
 **replace_with** | **int**| The ID of the option that will replace the currently selected option. | [optional] 
 **jql** | **str**| A JQL query that specifies the issues to be updated. For example, *project&#x3D;10000*. | [optional] 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_custom_field_option**
> CustomFieldUpdatedContextOptionsList update_custom_field_option(body, field_id, context_id)

Update custom field options (context)

Updates the options of a custom field.  If any of the options are not found, no options are updated. Options where the values in the request match the current values aren't updated and aren't reported in the response.  Note that this operation **only works for issue field select list options created in Jira or using operations from the [Issue custom field options](#api-group-Issue-custom-field-options) resource**, it cannot be used with issue field select list options created by Connect apps.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueCustomFieldOptionsApi(jira_client.ApiClient(configuration))
body = jira_client.BulkCustomFieldOptionUpdateRequest() # BulkCustomFieldOptionUpdateRequest | 
field_id = 'field_id_example' # str | The ID of the custom field.
context_id = 789 # int | The ID of the context.

try:
    # Update custom field options (context)
    api_response = api_instance.update_custom_field_option(body, field_id, context_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldOptionsApi->update_custom_field_option: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkCustomFieldOptionUpdateRequest**](BulkCustomFieldOptionUpdateRequest.md)|  | 
 **field_id** | **str**| The ID of the custom field. | 
 **context_id** | **int**| The ID of the context. | 

### Return type

[**CustomFieldUpdatedContextOptionsList**](CustomFieldUpdatedContextOptionsList.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

