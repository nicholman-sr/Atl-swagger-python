# jira_client.WebhooksApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_webhook_by_id**](WebhooksApi.md#delete_webhook_by_id) | **DELETE** /rest/api/3/webhook | Delete webhooks by ID
[**get_dynamic_webhooks_for_app**](WebhooksApi.md#get_dynamic_webhooks_for_app) | **GET** /rest/api/3/webhook | Get dynamic webhooks for app
[**get_failed_webhooks**](WebhooksApi.md#get_failed_webhooks) | **GET** /rest/api/3/webhook/failed | Get failed webhooks
[**refresh_webhooks**](WebhooksApi.md#refresh_webhooks) | **PUT** /rest/api/3/webhook/refresh | Extend webhook life
[**register_dynamic_webhooks**](WebhooksApi.md#register_dynamic_webhooks) | **POST** /rest/api/3/webhook | Register dynamic webhooks

# **delete_webhook_by_id**
> delete_webhook_by_id(body)

Delete webhooks by ID

Removes webhooks by ID. Only webhooks registered by the calling app are removed. If webhooks created by other apps are specified, they are ignored.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/#connect-apps) and [OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps) apps can use this operation.

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
api_instance = jira_client.WebhooksApi(jira_client.ApiClient(configuration))
body = jira_client.ContainerForWebhookIDs() # ContainerForWebhookIDs | 

try:
    # Delete webhooks by ID
    api_instance.delete_webhook_by_id(body)
except ApiException as e:
    print("Exception when calling WebhooksApi->delete_webhook_by_id: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ContainerForWebhookIDs**](ContainerForWebhookIDs.md)|  | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_dynamic_webhooks_for_app**
> PageBeanWebhook get_dynamic_webhooks_for_app(start_at=start_at, max_results=max_results)

Get dynamic webhooks for app

Returns a [paginated](#pagination) list of the webhooks registered by the calling app.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/#connect-apps) and [OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps) apps can use this operation.

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
api_instance = jira_client.WebhooksApi(jira_client.ApiClient(configuration))
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 100 # int | The maximum number of items to return per page. (optional) (default to 100)

try:
    # Get dynamic webhooks for app
    api_response = api_instance.get_dynamic_webhooks_for_app(start_at=start_at, max_results=max_results)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->get_dynamic_webhooks_for_app: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 100]

### Return type

[**PageBeanWebhook**](PageBeanWebhook.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_failed_webhooks**
> FailedWebhooks get_failed_webhooks(max_results=max_results, after=after)

Get failed webhooks

Returns webhooks that have recently failed to be delivered to the requesting app after the maximum number of retries.  After 72 hours the failure may no longer be returned by this operation.  The oldest failure is returned first.  This method uses a cursor-based pagination. To request the next page use the failure time of the last webhook on the list as the `failedAfter` value or use the URL provided in `next`.  **[Permissions](#permissions) required:** Only [Connect apps](https://developer.atlassian.com/cloud/jira/platform/index/#connect-apps) can use this operation.

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
api_instance = jira_client.WebhooksApi(jira_client.ApiClient(configuration))
max_results = 56 # int | The maximum number of webhooks to return per page. If obeying the maxResults directive would result in records with the same failure time being split across pages, the directive is ignored and all records with the same failure time included on the page. (optional)
after = 789 # int | The time after which any webhook failure must have occurred for the record to be returned, expressed as milliseconds since the UNIX epoch. (optional)

try:
    # Get failed webhooks
    api_response = api_instance.get_failed_webhooks(max_results=max_results, after=after)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->get_failed_webhooks: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **max_results** | **int**| The maximum number of webhooks to return per page. If obeying the maxResults directive would result in records with the same failure time being split across pages, the directive is ignored and all records with the same failure time included on the page. | [optional] 
 **after** | **int**| The time after which any webhook failure must have occurred for the record to be returned, expressed as milliseconds since the UNIX epoch. | [optional] 

### Return type

[**FailedWebhooks**](FailedWebhooks.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **refresh_webhooks**
> WebhooksExpirationDate refresh_webhooks(body)

Extend webhook life

Extends the life of webhook. Webhooks registered through the REST API expire after 30 days. Call this operation to keep them alive.  Unrecognized webhook IDs (those that are not found or belong to other apps) are ignored.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/#connect-apps) and [OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps) apps can use this operation.

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
api_instance = jira_client.WebhooksApi(jira_client.ApiClient(configuration))
body = jira_client.ContainerForWebhookIDs() # ContainerForWebhookIDs | 

try:
    # Extend webhook life
    api_response = api_instance.refresh_webhooks(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->refresh_webhooks: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ContainerForWebhookIDs**](ContainerForWebhookIDs.md)|  | 

### Return type

[**WebhooksExpirationDate**](WebhooksExpirationDate.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **register_dynamic_webhooks**
> ContainerForRegisteredWebhooks register_dynamic_webhooks(body)

Register dynamic webhooks

Registers webhooks.  **NOTE:** for non-public OAuth apps, webhooks are delivered only if there is a match between the app owner and the user who registered a dynamic webhook.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/#connect-apps) and [OAuth 2.0](https://developer.atlassian.com/cloud/jira/platform/oauth-2-3lo-apps) apps can use this operation.

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
api_instance = jira_client.WebhooksApi(jira_client.ApiClient(configuration))
body = jira_client.WebhookRegistrationDetails() # WebhookRegistrationDetails | 

try:
    # Register dynamic webhooks
    api_response = api_instance.register_dynamic_webhooks(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WebhooksApi->register_dynamic_webhooks: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WebhookRegistrationDetails**](WebhookRegistrationDetails.md)|  | 

### Return type

[**ContainerForRegisteredWebhooks**](ContainerForRegisteredWebhooks.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

