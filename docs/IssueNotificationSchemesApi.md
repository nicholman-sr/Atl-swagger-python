# jira_client.IssueNotificationSchemesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_notifications**](IssueNotificationSchemesApi.md#add_notifications) | **PUT** /rest/api/3/notificationscheme/{id}/notification | Add notifications to notification scheme
[**create_notification_scheme**](IssueNotificationSchemesApi.md#create_notification_scheme) | **POST** /rest/api/3/notificationscheme | Create notification scheme
[**delete_notification_scheme**](IssueNotificationSchemesApi.md#delete_notification_scheme) | **DELETE** /rest/api/3/notificationscheme/{notificationSchemeId} | Delete notification scheme
[**get_notification_scheme**](IssueNotificationSchemesApi.md#get_notification_scheme) | **GET** /rest/api/3/notificationscheme/{id} | Get notification scheme
[**get_notification_scheme_to_project_mappings**](IssueNotificationSchemesApi.md#get_notification_scheme_to_project_mappings) | **GET** /rest/api/3/notificationscheme/project | Get projects using notification schemes paginated
[**get_notification_schemes**](IssueNotificationSchemesApi.md#get_notification_schemes) | **GET** /rest/api/3/notificationscheme | Get notification schemes paginated
[**remove_notification_from_notification_scheme**](IssueNotificationSchemesApi.md#remove_notification_from_notification_scheme) | **DELETE** /rest/api/3/notificationscheme/{notificationSchemeId}/notification/{notificationId} | Remove notification from notification scheme
[**update_notification_scheme**](IssueNotificationSchemesApi.md#update_notification_scheme) | **PUT** /rest/api/3/notificationscheme/{id} | Update notification scheme

# **add_notifications**
> object add_notifications(body, id)

Add notifications to notification scheme

Adds notifications to a notification scheme. You can add up to 1000 notifications per request.  *Deprecated: The notification type `EmailAddress` is no longer supported in Cloud. Refer to the [changelog](https://developer.atlassian.com/cloud/jira/platform/changelog/#CHANGE-1031) for more details.*  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
body = {
  "notificationSchemeEvents" : [ {
    "event" : {
      "id" : "1"
    },
    "notifications" : [ {
      "notificationType" : "Group",
      "parameter" : "jira-administrators"
    } ]
  } ]
} # dict(str, object) | 
id = 'id_example' # str | The ID of the notification scheme.

try:
    # Add notifications to notification scheme
    api_response = api_instance.add_notifications(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->add_notifications: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **id** | **str**| The ID of the notification scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_notification_scheme**
> NotificationSchemeId create_notification_scheme(body)

Create notification scheme

Creates a notification scheme with notifications. You can create up to 1000 notifications per request.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My new scheme description",
  "name" : "My new notification scheme",
  "notificationSchemeEvents" : [ {
    "event" : {
      "id" : "1"
    },
    "notifications" : [ {
      "notificationType" : "Group",
      "parameter" : "jira-administrators"
    } ]
  } ]
} # dict(str, object) | 

try:
    # Create notification scheme
    api_response = api_instance.create_notification_scheme(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->create_notification_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 

### Return type

[**NotificationSchemeId**](NotificationSchemeId.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_notification_scheme**
> object delete_notification_scheme(notification_scheme_id)

Delete notification scheme

Deletes a notification scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
notification_scheme_id = 'notification_scheme_id_example' # str | The ID of the notification scheme.

try:
    # Delete notification scheme
    api_response = api_instance.delete_notification_scheme(notification_scheme_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->delete_notification_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **notification_scheme_id** | **str**| The ID of the notification scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_notification_scheme**
> NotificationScheme get_notification_scheme(id, expand=expand)

Get notification scheme

Returns a [notification scheme](https://confluence.atlassian.com/x/8YdKLg), including the list of events and the recipients who will receive notifications for those events.  **[Permissions](#permissions) required:** Permission to access Jira, however, the user must have permission to administer at least one project associated with the notification scheme.

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
id = 789 # int | The ID of the notification scheme. Use [Get notification schemes paginated](#api-rest-api-3-notificationscheme-get) to get a list of notification scheme IDs.
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  `all` Returns all expandable information  *  `field` Returns information about any custom fields assigned to receive an event  *  `group` Returns information about any groups assigned to receive an event  *  `notificationSchemeEvents` Returns a list of event associations. This list is returned for all expandable information  *  `projectRole` Returns information about any project roles assigned to receive an event  *  `user` Returns information about any users assigned to receive an event (optional)

try:
    # Get notification scheme
    api_response = api_instance.get_notification_scheme(id, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->get_notification_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **int**| The ID of the notification scheme. Use [Get notification schemes paginated](#api-rest-api-3-notificationscheme-get) to get a list of notification scheme IDs. | 
 **expand** | **str**| Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;all&#x60; Returns all expandable information  *  &#x60;field&#x60; Returns information about any custom fields assigned to receive an event  *  &#x60;group&#x60; Returns information about any groups assigned to receive an event  *  &#x60;notificationSchemeEvents&#x60; Returns a list of event associations. This list is returned for all expandable information  *  &#x60;projectRole&#x60; Returns information about any project roles assigned to receive an event  *  &#x60;user&#x60; Returns information about any users assigned to receive an event | [optional] 

### Return type

[**NotificationScheme**](NotificationScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_notification_scheme_to_project_mappings**
> PageBeanNotificationSchemeAndProjectMappingJsonBean get_notification_scheme_to_project_mappings(start_at=start_at, max_results=max_results, notification_scheme_id=notification_scheme_id, project_id=project_id)

Get projects using notification schemes paginated

Returns a [paginated](#pagination) mapping of project that have notification scheme assigned. You can provide either one or multiple notification scheme IDs or project IDs to filter by. If you don't provide any, this will return a list of all mappings. Note that only company-managed (classic) projects are supported. This is because team-managed projects don't have a concept of a default notification scheme. The mappings are ordered by projectId.  **[Permissions](#permissions) required:** Permission to access Jira.

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
notification_scheme_id = ['notification_scheme_id_example'] # list[str] | The list of notifications scheme IDs to be filtered out (optional)
project_id = ['project_id_example'] # list[str] | The list of project IDs to be filtered out (optional)

try:
    # Get projects using notification schemes paginated
    api_response = api_instance.get_notification_scheme_to_project_mappings(start_at=start_at, max_results=max_results, notification_scheme_id=notification_scheme_id, project_id=project_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->get_notification_scheme_to_project_mappings: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **notification_scheme_id** | [**list[str]**](str.md)| The list of notifications scheme IDs to be filtered out | [optional] 
 **project_id** | [**list[str]**](str.md)| The list of project IDs to be filtered out | [optional] 

### Return type

[**PageBeanNotificationSchemeAndProjectMappingJsonBean**](PageBeanNotificationSchemeAndProjectMappingJsonBean.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_notification_schemes**
> PageBeanNotificationScheme get_notification_schemes(start_at=start_at, max_results=max_results, id=id, project_id=project_id, only_default=only_default, expand=expand)

Get notification schemes paginated

Returns a [paginated](#pagination) list of [notification schemes](https://confluence.atlassian.com/x/8YdKLg) ordered by the display name.  *Note that you should allow for events without recipients to appear in responses.*  **[Permissions](#permissions) required:** Permission to access Jira, however, the user must have permission to administer at least one project associated with a notification scheme for it to be returned.

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
start_at = '0' # str | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = '50' # str | The maximum number of items to return per page. (optional) (default to 50)
id = ['id_example'] # list[str] | The list of notification schemes IDs to be filtered by (optional)
project_id = ['project_id_example'] # list[str] | The list of projects IDs to be filtered by (optional)
only_default = false # bool | When set to true, returns only the default notification scheme. If you provide project IDs not associated with the default, returns an empty page. The default value is false. (optional) (default to false)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  `all` Returns all expandable information  *  `field` Returns information about any custom fields assigned to receive an event  *  `group` Returns information about any groups assigned to receive an event  *  `notificationSchemeEvents` Returns a list of event associations. This list is returned for all expandable information  *  `projectRole` Returns information about any project roles assigned to receive an event  *  `user` Returns information about any users assigned to receive an event (optional)

try:
    # Get notification schemes paginated
    api_response = api_instance.get_notification_schemes(start_at=start_at, max_results=max_results, id=id, project_id=project_id, only_default=only_default, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->get_notification_schemes: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **start_at** | **str**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **str**| The maximum number of items to return per page. | [optional] [default to 50]
 **id** | [**list[str]**](str.md)| The list of notification schemes IDs to be filtered by | [optional] 
 **project_id** | [**list[str]**](str.md)| The list of projects IDs to be filtered by | [optional] 
 **only_default** | **bool**| When set to true, returns only the default notification scheme. If you provide project IDs not associated with the default, returns an empty page. The default value is false. | [optional] [default to false]
 **expand** | **str**| Use [expand](#expansion) to include additional information in the response. This parameter accepts a comma-separated list. Expand options include:   *  &#x60;all&#x60; Returns all expandable information  *  &#x60;field&#x60; Returns information about any custom fields assigned to receive an event  *  &#x60;group&#x60; Returns information about any groups assigned to receive an event  *  &#x60;notificationSchemeEvents&#x60; Returns a list of event associations. This list is returned for all expandable information  *  &#x60;projectRole&#x60; Returns information about any project roles assigned to receive an event  *  &#x60;user&#x60; Returns information about any users assigned to receive an event | [optional] 

### Return type

[**PageBeanNotificationScheme**](PageBeanNotificationScheme.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_notification_from_notification_scheme**
> object remove_notification_from_notification_scheme(notification_scheme_id, notification_id)

Remove notification from notification scheme

Removes a notification from a notification scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
notification_scheme_id = 'notification_scheme_id_example' # str | The ID of the notification scheme.
notification_id = 'notification_id_example' # str | The ID of the notification.

try:
    # Remove notification from notification scheme
    api_response = api_instance.remove_notification_from_notification_scheme(notification_scheme_id, notification_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->remove_notification_from_notification_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **notification_scheme_id** | **str**| The ID of the notification scheme. | 
 **notification_id** | **str**| The ID of the notification. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_notification_scheme**
> object update_notification_scheme(body, id)

Update notification scheme

Updates a notification scheme.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.IssueNotificationSchemesApi(jira_client.ApiClient(configuration))
body = {
  "description" : "My updated notification scheme description",
  "name" : "My updated notification scheme"
} # dict(str, object) | 
id = 'id_example' # str | The ID of the notification scheme.

try:
    # Update notification scheme
    api_response = api_instance.update_notification_scheme(body, id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueNotificationSchemesApi->update_notification_scheme: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**dict(str, object)**](dict.md)|  | 
 **id** | **str**| The ID of the notification scheme. | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

