# jira_client.AnnouncementBannerApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_banner**](AnnouncementBannerApi.md#get_banner) | **GET** /rest/api/3/announcementBanner | Get announcement banner configuration
[**set_banner**](AnnouncementBannerApi.md#set_banner) | **PUT** /rest/api/3/announcementBanner | Update announcement banner configuration

# **get_banner**
> AnnouncementBannerConfiguration get_banner()

Get announcement banner configuration

Returns the current announcement banner configuration.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.AnnouncementBannerApi(jira_client.ApiClient(configuration))

try:
    # Get announcement banner configuration
    api_response = api_instance.get_banner()
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AnnouncementBannerApi->get_banner: %s\n" % e)
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**AnnouncementBannerConfiguration**](AnnouncementBannerConfiguration.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_banner**
> object set_banner(body)

Update announcement banner configuration

Updates the announcement banner configuration.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.AnnouncementBannerApi(jira_client.ApiClient(configuration))
body = jira_client.AnnouncementBannerConfigurationUpdate() # AnnouncementBannerConfigurationUpdate | 

try:
    # Update announcement banner configuration
    api_response = api_instance.set_banner(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AnnouncementBannerApi->set_banner: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**AnnouncementBannerConfigurationUpdate**](AnnouncementBannerConfigurationUpdate.md)|  | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

