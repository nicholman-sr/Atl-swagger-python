# jira_client.DynamicModulesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**dynamic_modules_resource_get_modules_get**](DynamicModulesApi.md#dynamic_modules_resource_get_modules_get) | **GET** /rest/atlassian-connect/1/app/module/dynamic | Get modules
[**dynamic_modules_resource_register_modules_post**](DynamicModulesApi.md#dynamic_modules_resource_register_modules_post) | **POST** /rest/atlassian-connect/1/app/module/dynamic | Register modules
[**dynamic_modules_resource_remove_modules_delete**](DynamicModulesApi.md#dynamic_modules_resource_remove_modules_delete) | **DELETE** /rest/atlassian-connect/1/app/module/dynamic | Remove modules

# **dynamic_modules_resource_get_modules_get**
> ConnectModules dynamic_modules_resource_get_modules_get()

Get modules

Returns all modules registered dynamically by the calling app.  **[Permissions](#permissions) required:** Only Connect apps can make this request.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.DynamicModulesApi()

try:
    # Get modules
    api_response = api_instance.dynamic_modules_resource_get_modules_get()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling DynamicModulesApi->dynamic_modules_resource_get_modules_get: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**ConnectModules**](ConnectModules.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **dynamic_modules_resource_register_modules_post**
> dynamic_modules_resource_register_modules_post(body)

Register modules

Registers a list of modules.  **[Permissions](#permissions) required:** Only Connect apps can make this request.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.DynamicModulesApi()
body = jira_client.ConnectModules() # ConnectModules | 

try:
    # Register modules
    api_instance.dynamic_modules_resource_register_modules_post(body)
except ApiException as e:
    print("Exception when calling DynamicModulesApi->dynamic_modules_resource_register_modules_post: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ConnectModules**](ConnectModules.md)|  | 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **dynamic_modules_resource_remove_modules_delete**
> dynamic_modules_resource_remove_modules_delete(module_key=module_key)

Remove modules

Remove all or a list of modules registered by the calling app.  **[Permissions](#permissions) required:** Only Connect apps can make this request.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.DynamicModulesApi()
module_key = ['module_key_example'] # list[str] | The key of the module to remove. To include multiple module keys, provide multiple copies of this parameter. For example, `moduleKey=dynamic-attachment-entity-property&moduleKey=dynamic-select-field`. Nonexistent keys are ignored. (optional)

try:
    # Remove modules
    api_instance.dynamic_modules_resource_remove_modules_delete(module_key=module_key)
except ApiException as e:
    print("Exception when calling DynamicModulesApi->dynamic_modules_resource_remove_modules_delete: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **module_key** | [**list[str]**](str.md)| The key of the module to remove. To include multiple module keys, provide multiple copies of this parameter. For example, &#x60;moduleKey&#x3D;dynamic-attachment-entity-property&amp;moduleKey&#x3D;dynamic-select-field&#x60;. Nonexistent keys are ignored. | [optional] 

### Return type

void (empty response body)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

