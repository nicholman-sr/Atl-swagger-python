# jira_client.IssueRedactionApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_redaction_status**](IssueRedactionApi.md#get_redaction_status) | **GET** /rest/api/3/redact/status/{jobId} | Get redaction status
[**redact**](IssueRedactionApi.md#redact) | **POST** /rest/api/3/redact | Redact

# **get_redaction_status**
> RedactionJobStatusResponse get_redaction_status(job_id)

Get redaction status

Retrieves the current status of a redaction job ID.  The jobStatus will be one of the following:   *  IN\\_PROGRESS - The redaction job is currently in progress  *  COMPLETED - The redaction job has completed successfully.  *  PENDING - The redaction job has not started yet

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.IssueRedactionApi(jira_client.ApiClient(configuration))
job_id = 'job_id_example' # str | Redaction job id

try:
    # Get redaction status
    api_response = api_instance.get_redaction_status(job_id)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRedactionApi->get_redaction_status: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **job_id** | **str**| Redaction job id | 

### Return type

[**RedactionJobStatusResponse**](RedactionJobStatusResponse.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **redact**
> str redact(body)

Redact

Submit a job to redact issue field data. This will trigger the redaction of the data in the specified fields asynchronously.  The redaction status can be polled using the job id.

### Example
```python
from __future__ import print_function
import time
import jira_client
from jira_client.rest import ApiException
from pprint import pprint
# Configure HTTP basic authorization: basicAuth
configuration = jira_client.Configuration()
configuration.username = 'YOUR_USERNAME'
configuration.password = 'YOUR_PASSWORD'

# create an instance of the API class
api_instance = jira_client.IssueRedactionApi(jira_client.ApiClient(configuration))
body = jira_client.BulkRedactionRequest() # BulkRedactionRequest | List of redaction requests

try:
    # Redact
    api_response = api_instance.redact(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling IssueRedactionApi->redact: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**BulkRedactionRequest**](BulkRedactionRequest.md)| List of redaction requests | 

### Return type

**str**

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

