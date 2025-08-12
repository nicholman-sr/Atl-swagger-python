# jira_client.LicenseMetricsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_approximate_application_license_count**](LicenseMetricsApi.md#get_approximate_application_license_count) | **GET** /rest/api/3/license/approximateLicenseCount/product/{applicationKey} | Get approximate application license count
[**get_approximate_license_count**](LicenseMetricsApi.md#get_approximate_license_count) | **GET** /rest/api/3/license/approximateLicenseCount | Get approximate license count
[**get_license**](LicenseMetricsApi.md#get_license) | **GET** /rest/api/3/instance/license | Get license

# **get_approximate_application_license_count**
> LicenseMetric get_approximate_application_license_count(application_key)

Get approximate application license count

Returns the total approximate number of user accounts for a single Jira license. Note that this information is cached with a 7-day lifecycle and could be stale at the time of call.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.LicenseMetricsApi(jira_client.ApiClient(configuration))
application_key = 'application_key_example' # str | The ID of the application, represents a specific version of Jira.

try:
    # Get approximate application license count
    api_response = api_instance.get_approximate_application_license_count(application_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling LicenseMetricsApi->get_approximate_application_license_count: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **application_key** | **str**| The ID of the application, represents a specific version of Jira. | 

### Return type

[**LicenseMetric**](LicenseMetric.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_approximate_license_count**
> LicenseMetric get_approximate_license_count()

Get approximate license count

Returns the approximate number of user accounts across all Jira licenses. Note that this information is cached with a 7-day lifecycle and could be stale at the time of call.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.LicenseMetricsApi(jira_client.ApiClient(configuration))

try:
    # Get approximate license count
    api_response = api_instance.get_approximate_license_count()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling LicenseMetricsApi->get_approximate_license_count: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**LicenseMetric**](LicenseMetric.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_license**
> License get_license()

Get license

Returns licensing information about the Jira instance.  **[Permissions](#permissions) required:** None.

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
api_instance = jira_client.LicenseMetricsApi(jira_client.ApiClient(configuration))

try:
    # Get license
    api_response = api_instance.get_license()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling LicenseMetricsApi->get_license: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**License**](License.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

