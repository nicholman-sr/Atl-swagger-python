# jira_client.ServiceRegistryApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**service_registry_resource_services_get**](ServiceRegistryApi.md#service_registry_resource_services_get) | **GET** /rest/atlassian-connect/1/service-registry | Retrieve the attributes of service registries

# **service_registry_resource_services_get**
> list[ServiceRegistry] service_registry_resource_services_get(service_ids)

Retrieve the attributes of service registries

Retrieve the attributes of given service registries.  **[Permissions](#permissions) required:** Only Connect apps can make this request and the servicesIds belong to the tenant you are requesting

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint

# create an instance of the API class
api_instance = jira_client.ServiceRegistryApi()
service_ids = ['service_ids_example'] # list[str] | The ID of the services (the strings starting with \"b:\" need to be decoded in Base64).

try:
    # Retrieve the attributes of service registries
    api_response = api_instance.service_registry_resource_services_get(service_ids)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ServiceRegistryApi->service_registry_resource_services_get: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **service_ids** | [**list[str]**](str.md)| The ID of the services (the strings starting with \&quot;b:\&quot; need to be decoded in Base64). | 

### Return type

[**list[ServiceRegistry]**](ServiceRegistry.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

