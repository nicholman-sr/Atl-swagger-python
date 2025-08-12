# jira_client.TimeTrackingApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_available_time_tracking_implementations**](TimeTrackingApi.md#get_available_time_tracking_implementations) | **GET** /rest/api/3/configuration/timetracking/list | Get all time tracking providers
[**get_selected_time_tracking_implementation**](TimeTrackingApi.md#get_selected_time_tracking_implementation) | **GET** /rest/api/3/configuration/timetracking | Get selected time tracking provider
[**get_shared_time_tracking_configuration**](TimeTrackingApi.md#get_shared_time_tracking_configuration) | **GET** /rest/api/3/configuration/timetracking/options | Get time tracking settings
[**select_time_tracking_implementation**](TimeTrackingApi.md#select_time_tracking_implementation) | **PUT** /rest/api/3/configuration/timetracking | Select time tracking provider
[**set_shared_time_tracking_configuration**](TimeTrackingApi.md#set_shared_time_tracking_configuration) | **PUT** /rest/api/3/configuration/timetracking/options | Set time tracking settings

# **get_available_time_tracking_implementations**
> list[TimeTrackingProvider] get_available_time_tracking_implementations()

Get all time tracking providers

Returns all time tracking providers. By default, Jira only has one time tracking provider: *JIRA provided time tracking*. However, you can install other time tracking providers via apps from the Atlassian Marketplace. For more information on time tracking providers, see the documentation for the [ Time Tracking Provider](https://developer.atlassian.com/cloud/jira/platform/modules/time-tracking-provider/) module.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TimeTrackingApi(jira_client.ApiClient(configuration))

try:
    # Get all time tracking providers
    api_response = api_instance.get_available_time_tracking_implementations()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TimeTrackingApi->get_available_time_tracking_implementations: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**list[TimeTrackingProvider]**](TimeTrackingProvider.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_selected_time_tracking_implementation**
> TimeTrackingProvider get_selected_time_tracking_implementation()

Get selected time tracking provider

Returns the time tracking provider that is currently selected. Note that if time tracking is disabled, then a successful but empty response is returned.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TimeTrackingApi(jira_client.ApiClient(configuration))

try:
    # Get selected time tracking provider
    api_response = api_instance.get_selected_time_tracking_implementation()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TimeTrackingApi->get_selected_time_tracking_implementation: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**TimeTrackingProvider**](TimeTrackingProvider.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_shared_time_tracking_configuration**
> TimeTrackingConfiguration get_shared_time_tracking_configuration()

Get time tracking settings

Returns the time tracking settings. This includes settings such as the time format, default time unit, and others. For more information, see [Configuring time tracking](https://confluence.atlassian.com/x/qoXKM).  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TimeTrackingApi(jira_client.ApiClient(configuration))

try:
    # Get time tracking settings
    api_response = api_instance.get_shared_time_tracking_configuration()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TimeTrackingApi->get_shared_time_tracking_configuration: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**TimeTrackingConfiguration**](TimeTrackingConfiguration.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **select_time_tracking_implementation**
> object select_time_tracking_implementation(body)

Select time tracking provider

Selects a time tracking provider.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TimeTrackingApi(jira_client.ApiClient(configuration))
body = jira_client.TimeTrackingProvider() # TimeTrackingProvider | 

try:
    # Select time tracking provider
    api_response = api_instance.select_time_tracking_implementation(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TimeTrackingApi->select_time_tracking_implementation: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**TimeTrackingProvider**](TimeTrackingProvider.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_shared_time_tracking_configuration**
> TimeTrackingConfiguration set_shared_time_tracking_configuration(body)

Set time tracking settings

Sets the time tracking settings.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.TimeTrackingApi(jira_client.ApiClient(configuration))
body = jira_client.TimeTrackingConfiguration() # TimeTrackingConfiguration | 

try:
    # Set time tracking settings
    api_response = api_instance.set_shared_time_tracking_configuration(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling TimeTrackingApi->set_shared_time_tracking_configuration: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**TimeTrackingConfiguration**](TimeTrackingConfiguration.md)|  | 

### Return type

[**TimeTrackingConfiguration**](TimeTrackingConfiguration.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

