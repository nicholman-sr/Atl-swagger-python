# jira_client.AppMigrationApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**app_issue_field_value_update_resource_update_issue_fields_put**](AppMigrationApi.md#app_issue_field_value_update_resource_update_issue_fields_put) | **PUT** /rest/atlassian-connect/1/migration/field | Bulk update custom field value
[**migration_resource_update_entity_properties_value_put**](AppMigrationApi.md#migration_resource_update_entity_properties_value_put) | **PUT** /rest/atlassian-connect/1/migration/properties/{entityType} | Bulk update entity properties
[**migration_resource_workflow_rule_search_post**](AppMigrationApi.md#migration_resource_workflow_rule_search_post) | **POST** /rest/atlassian-connect/1/migration/workflow/rule/search | Get workflow transition rule configurations

# **app_issue_field_value_update_resource_update_issue_fields_put**
> object app_issue_field_value_update_resource_update_issue_fields_put(body, atlassian_transfer_id)

Bulk update custom field value

Updates the value of a custom field added by Connect apps on one or more issues. The values of up to 200 custom fields can be updated.  **[Permissions](#permissions) required:** Only Connect apps can make this request

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.AppMigrationApi()
body = jira_client.ConnectCustomFieldValues() # ConnectCustomFieldValues | 
atlassian_transfer_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # str | The ID of the transfer.

try:
    # Bulk update custom field value
    api_response = api_instance.app_issue_field_value_update_resource_update_issue_fields_put(body, atlassian_transfer_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AppMigrationApi->app_issue_field_value_update_resource_update_issue_fields_put: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ConnectCustomFieldValues**](ConnectCustomFieldValues.md)|  | 
 **atlassian_transfer_id** | [**str**](.md)| The ID of the transfer. | 

### Return type

**object**

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **migration_resource_update_entity_properties_value_put**
> migration_resource_update_entity_properties_value_put(body, atlassian_transfer_id, entity_type)

Bulk update entity properties

Updates the values of multiple entity properties for an object, up to 50 updates per request. This operation is for use by Connect apps during app migration.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.AppMigrationApi()
body = [jira_client.EntityPropertyDetails()] # list[EntityPropertyDetails] | 
atlassian_transfer_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # str | The app migration transfer ID.
entity_type = 'entity_type_example' # str | The type indicating the object that contains the entity properties.

try:
    # Bulk update entity properties
    api_instance.migration_resource_update_entity_properties_value_put(body, atlassian_transfer_id, entity_type)
except ApiException as e:
    print("Exception when calling AppMigrationApi->migration_resource_update_entity_properties_value_put: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**list[EntityPropertyDetails]**](EntityPropertyDetails.md)|  | 
 **atlassian_transfer_id** | [**str**](.md)| The app migration transfer ID. | 
 **entity_type** | **str**| The type indicating the object that contains the entity properties. | 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: Not defined

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **migration_resource_workflow_rule_search_post**
> WorkflowRulesSearchDetails migration_resource_workflow_rule_search_post(body, atlassian_transfer_id)

Get workflow transition rule configurations

Returns configurations for workflow transition rules migrated from server to cloud and owned by the calling Connect app.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.AppMigrationApi()
body = jira_client.WorkflowRulesSearch() # WorkflowRulesSearch | 
atlassian_transfer_id = '38400000-8cf0-11bd-b23e-10b96e4ef00d' # str | The app migration transfer ID.

try:
    # Get workflow transition rule configurations
    api_response = api_instance.migration_resource_workflow_rule_search_post(body, atlassian_transfer_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AppMigrationApi->migration_resource_workflow_rule_search_post: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowRulesSearch**](WorkflowRulesSearch.md)|  | 
 **atlassian_transfer_id** | [**str**](.md)| The app migration transfer ID. | 

### Return type

[**WorkflowRulesSearchDetails**](WorkflowRulesSearchDetails.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

