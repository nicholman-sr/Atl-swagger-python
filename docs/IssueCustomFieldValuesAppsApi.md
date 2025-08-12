# jira_client.IssueCustomFieldValuesAppsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**update_custom_field_value**](IssueCustomFieldValuesAppsApi.md#update_custom_field_value) | **PUT** /rest/api/3/app/field/{fieldIdOrKey}/value | Update custom field value
[**update_multiple_custom_field_values**](IssueCustomFieldValuesAppsApi.md#update_multiple_custom_field_values) | **POST** /rest/api/3/app/field/value | Update custom fields

# **update_custom_field_value**
> object update_custom_field_value(body, field_id_or_key, generate_changelog=generate_changelog)

Update custom field value

Updates the value of a custom field on one or more issues.  Apps can only perform this operation on [custom fields](https://developer.atlassian.com/platform/forge/manifest-reference/modules/jira-custom-field/) and [custom field types](https://developer.atlassian.com/platform/forge/manifest-reference/modules/jira-custom-field-type/) declared in their own manifests.  **[Permissions](#permissions) required:** Only the app that owns the custom field or custom field type can update its values with this operation.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.IssueCustomFieldValuesAppsApi(jira_client.ApiClient(configuration))
body = jira_client.CustomFieldValueUpdateDetails() # CustomFieldValueUpdateDetails | 
field_id_or_key = 'field_id_or_key_example' # str | The ID or key of the custom field. For example, `customfield_10010`.
generate_changelog = true # bool | Whether to generate a changelog for this update. (optional) (default to true)

try:
    # Update custom field value
    api_response = api_instance.update_custom_field_value(body, field_id_or_key, generate_changelog=generate_changelog)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldValuesAppsApi->update_custom_field_value: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**CustomFieldValueUpdateDetails**](CustomFieldValueUpdateDetails.md)|  | 
 **field_id_or_key** | **str**| The ID or key of the custom field. For example, &#x60;customfield_10010&#x60;. | 
 **generate_changelog** | **bool**| Whether to generate a changelog for this update. | [optional] [default to true]

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_multiple_custom_field_values**
> object update_multiple_custom_field_values(body, generate_changelog=generate_changelog)

Update custom fields

Updates the value of one or more custom fields on one or more issues. Combinations of custom field and issue should be unique within the request.  Apps can only perform this operation on [custom fields](https://developer.atlassian.com/platform/forge/manifest-reference/modules/jira-custom-field/) and [custom field types](https://developer.atlassian.com/platform/forge/manifest-reference/modules/jira-custom-field-type/) declared in their own manifests.  **[Permissions](#permissions) required:** Only the app that owns the custom field or custom field type can update its values with this operation.  The new `write:app-data:jira` OAuth scope is 100% optional now, and not using it won't break your app. However, we recommend adding it to your app's scope list because we will eventually make it mandatory.

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
api_instance = jira_client.IssueCustomFieldValuesAppsApi(jira_client.ApiClient(configuration))
body = jira_client.MultipleCustomFieldValuesUpdateDetails() # MultipleCustomFieldValuesUpdateDetails | 
generate_changelog = true # bool | Whether to generate a changelog for this update. (optional) (default to true)

try:
    # Update custom fields
    api_response = api_instance.update_multiple_custom_field_values(body, generate_changelog=generate_changelog)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueCustomFieldValuesAppsApi->update_multiple_custom_field_values: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**MultipleCustomFieldValuesUpdateDetails**](MultipleCustomFieldValuesUpdateDetails.md)|  | 
 **generate_changelog** | **bool**| Whether to generate a changelog for this update. | [optional] [default to true]

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

