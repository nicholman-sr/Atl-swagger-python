# jira_client.AuditRecordsApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_audit_records**](AuditRecordsApi.md#get_audit_records) | **GET** /rest/api/3/auditing/record | Get audit records

# **get_audit_records**
> AuditRecords get_audit_records(offset=offset, limit=limit, filter=filter, _from=_from, to=to)

Get audit records

Returns a list of audit records. The list can be filtered to include items:   *  where each item in `filter` has at least one match in any of these fields:           *  `summary`      *  `category`      *  `eventSource`      *  `objectItem.name` If the object is a user, account ID is available to filter.      *  `objectItem.parentName`      *  `objectItem.typeName`      *  `changedValues.changedFrom`      *  `changedValues.changedTo`      *  `remoteAddress`          For example, if `filter` contains *man ed*, an audit record containing `summary\": \"User added to group\"` and `\"category\": \"group management\"` is returned.  *  created on or after a date and time.  *  created or or before a date and time.  **[Permissions](#permissions) required:** *Administer Jira* [global permission](https://confluence.atlassian.com/x/x4dKLg).

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
api_instance = jira_client.AuditRecordsApi(jira_client.ApiClient(configuration))
offset = 0 # int | The number of records to skip before returning the first result. (optional) (default to 0)
limit = 1000 # int | The maximum number of results to return. (optional) (default to 1000)
filter = 'filter_example' # str | The strings to match with audit field content, space separated. (optional)
_from = '_from_example' # str | The date and time on or after which returned audit records must have been created. If `to` is provided `from` must be before `to` or no audit records are returned. (optional)
to = 'to_example' # str | The date and time on or before which returned audit results must have been created. If `from` is provided `to` must be after `from` or no audit records are returned. (optional)

try:
    # Get audit records
    api_response = api_instance.get_audit_records(offset=offset, limit=limit, filter=filter, _from=_from, to=to)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling AuditRecordsApi->get_audit_records: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **offset** | **int**| The number of records to skip before returning the first result. | [optional] [default to 0]
 **limit** | **int**| The maximum number of results to return. | [optional] [default to 1000]
 **filter** | **str**| The strings to match with audit field content, space separated. | [optional] 
 **_from** | **str**| The date and time on or after which returned audit records must have been created. If &#x60;to&#x60; is provided &#x60;from&#x60; must be before &#x60;to&#x60; or no audit records are returned. | [optional] 
 **to** | **str**| The date and time on or before which returned audit results must have been created. If &#x60;from&#x60; is provided &#x60;to&#x60; must be after &#x60;from&#x60; or no audit records are returned. | [optional] 

### Return type

[**AuditRecords**](AuditRecords.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

