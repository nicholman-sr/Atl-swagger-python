# jira_client.ProjectTemplatesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_project_with_custom_template**](ProjectTemplatesApi.md#create_project_with_custom_template) | **POST** /rest/api/3/project-template | Create custom project
[**edit_template**](ProjectTemplatesApi.md#edit_template) | **PUT** /rest/api/3/project-template/edit-template | Edit a custom project template
[**live_template**](ProjectTemplatesApi.md#live_template) | **GET** /rest/api/3/project-template/live-template | Gets a custom project template
[**remove_template**](ProjectTemplatesApi.md#remove_template) | **DELETE** /rest/api/3/project-template/remove-template | Deletes a custom project template
[**save_template**](ProjectTemplatesApi.md#save_template) | **POST** /rest/api/3/project-template/save-template | Save a custom project template

# **create_project_with_custom_template**
> create_project_with_custom_template(body)

Create custom project

Creates a project based on a custom template provided in the request.  The request body should contain the project details and the capabilities that comprise the project:   *  `details` \\- represents the project details settings  *  `template` \\- represents a list of capabilities responsible for creating specific parts of a project  A capability is defined as a unit of configuration for the project you want to create.  This operation is:   *  [asynchronous](#async). Follow the `Location` link in the response header to determine the status of the task and use [Get task](#api-rest-api-3-task-taskId-get) to obtain subsequent updates.  ***Note: This API is only supported for Jira Enterprise edition.***

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
api_instance = jira_client.ProjectTemplatesApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectCustomTemplateCreateRequestDTO() # ProjectCustomTemplateCreateRequestDTO | The JSON payload containing the project details and capabilities

try:
    # Create custom project
    api_instance.create_project_with_custom_template(body)
except ApiException as e:
    print("Exception when calling ProjectTemplatesApi->create_project_with_custom_template: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectCustomTemplateCreateRequestDTO**](ProjectCustomTemplateCreateRequestDTO.md)| The JSON payload containing the project details and capabilities | 

### Return type

void (empty response body)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **edit_template**
> object edit_template(body)

Edit a custom project template

Edit custom template  This API endpoint allows you to edit an existing customised template.  ***Note: Custom Templates are only supported for Jira Enterprise edition.***

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
api_instance = jira_client.ProjectTemplatesApi(jira_client.ApiClient(configuration))
body = jira_client.EditTemplateRequest() # EditTemplateRequest | The object containing the updated template details: name, description

try:
    # Edit a custom project template
    api_response = api_instance.edit_template(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTemplatesApi->edit_template: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**EditTemplateRequest**](EditTemplateRequest.md)| The object containing the updated template details: name, description | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **live_template**
> ProjectTemplateModel live_template(project_id=project_id, template_key=template_key)

Gets a custom project template

Get custom template  This API endpoint allows you to get a live custom project template details by either templateKey or projectId  ***Note: Custom Templates are only supported for Jira Enterprise edition.***

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
api_instance = jira_client.ProjectTemplatesApi(jira_client.ApiClient(configuration))
project_id = 'project_id_example' # str | optional - The \\{@link String\\} containing the project key linked to the custom template to retrieve (optional)
template_key = 'template_key_example' # str | optional - The \\{@link String\\} containing the key of the custom template to retrieve (optional)

try:
    # Gets a custom project template
    api_response = api_instance.live_template(project_id=project_id, template_key=template_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTemplatesApi->live_template: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id** | **str**| optional - The \\{@link String\\} containing the project key linked to the custom template to retrieve | [optional] 
 **template_key** | **str**| optional - The \\{@link String\\} containing the key of the custom template to retrieve | [optional] 

### Return type

[**ProjectTemplateModel**](ProjectTemplateModel.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_template**
> object remove_template(template_key)

Deletes a custom project template

Remove custom template  This API endpoint allows you to remove a specified customised template  ***Note: Custom Templates are only supported for Jira Enterprise edition.***

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
api_instance = jira_client.ProjectTemplatesApi(jira_client.ApiClient(configuration))
template_key = 'template_key_example' # str | The \\{@link String\\} containing the key of the custom template to remove

try:
    # Deletes a custom project template
    api_response = api_instance.remove_template(template_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTemplatesApi->remove_template: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **template_key** | **str**| The \\{@link String\\} containing the key of the custom template to remove | 

### Return type

**object**

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **save_template**
> SaveTemplateResponse save_template(body)

Save a custom project template

Save custom template  This API endpoint allows you to save a customised template  ***Note: Custom Templates are only supported for Jira Enterprise edition.***

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
api_instance = jira_client.ProjectTemplatesApi(jira_client.ApiClient(configuration))
body = jira_client.SaveTemplateRequest() # SaveTemplateRequest | The object containing the template basic details: name, description

try:
    # Save a custom project template
    api_response = api_instance.save_template(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectTemplatesApi->save_template: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**SaveTemplateRequest**](SaveTemplateRequest.md)| The object containing the template basic details: name, description | 

### Return type

[**SaveTemplateResponse**](SaveTemplateResponse.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

