# jira_client.UsernavpropertiesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_user_nav_property**](UsernavpropertiesApi.md#get_user_nav_property) | **GET** /rest/api/3/user/nav4-opt-property/{propertyKey} | Get user nav property
[**set_user_nav_property**](UsernavpropertiesApi.md#set_user_nav_property) | **PUT** /rest/api/3/user/nav4-opt-property/{propertyKey} | Set user nav property

# **get_user_nav_property**
> UserNavPropertyJsonBean get_user_nav_property(property_key, account_id=account_id)

Get user nav property

Returns the value of a user nav preference.  Note: This operation fetches the property key value directly from RbacClient.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), to get a property from any user.  *  Access to Jira, to get a property from the calling user's record.

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
api_instance = jira_client.UsernavpropertiesApi(jira_client.ApiClient(configuration))
property_key = 'property_key_example' # str | The key of the user's property.
account_id = 'account_id_example' # str | The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. (optional)

try:
    # Get user nav property
    api_response = api_instance.get_user_nav_property(property_key, account_id=account_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UsernavpropertiesApi->get_user_nav_property: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **property_key** | **str**| The key of the user&#x27;s property. | 
 **account_id** | **str**| The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. | [optional] 

### Return type

[**UserNavPropertyJsonBean**](UserNavPropertyJsonBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **set_user_nav_property**
> object set_user_nav_property(body, property_key, account_id=account_id)

Set user nav property

Sets the value of a Nav4 preference. Use this resource to store Nav4 preference data against a user in the Identity service.  **[Permissions](#permissions) required:**   *  *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg), to set a property on any user.  *  Access to Jira, to set a property on the calling user's record.

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
api_instance = jira_client.UsernavpropertiesApi(jira_client.ApiClient(configuration))
body = NULL # object | The value of the property. The value has to be a boolean [JSON](https://tools.ietf.org/html/rfc4627) value. The maximum length of the property value is 32768 bytes.
property_key = 'property_key_example' # str | The key of the nav property. The maximum length is 255 characters.
account_id = 'account_id_example' # str | The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. (optional)

try:
    # Set user nav property
    api_response = api_instance.set_user_nav_property(body, property_key, account_id=account_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling UsernavpropertiesApi->set_user_nav_property: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**object**](object.md)| The value of the property. The value has to be a boolean [JSON](https://tools.ietf.org/html/rfc4627) value. The maximum length of the property value is 32768 bytes. | 
 **property_key** | **str**| The key of the nav property. The maximum length is 255 characters. | 
 **account_id** | **str**| The account ID of the user, which uniquely identifies the user across all Atlassian products. For example, *5b10ac8d82e05b22cc7d4ef5*. | [optional] 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

