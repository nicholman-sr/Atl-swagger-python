# jira_client.ProjectFeaturesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_features_for_project**](ProjectFeaturesApi.md#get_features_for_project) | **GET** /rest/api/3/project/{projectIdOrKey}/features | Get project features
[**toggle_feature_for_project**](ProjectFeaturesApi.md#toggle_feature_for_project) | **PUT** /rest/api/3/project/{projectIdOrKey}/features/{featureKey} | Set project feature state

# **get_features_for_project**
> ContainerForProjectFeatures get_features_for_project(project_id_or_key)

Get project features

Returns the list of features for a project.

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
api_instance = jira_client.ProjectFeaturesApi(jira_client.ApiClient(configuration))
project_id_or_key = 'project_id_or_key_example' # str | The ID or (case-sensitive) key of the project.

try:
    # Get project features
    api_response = api_instance.get_features_for_project(project_id_or_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectFeaturesApi->get_features_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **project_id_or_key** | **str**| The ID or (case-sensitive) key of the project. | 

### Return type

[**ContainerForProjectFeatures**](ContainerForProjectFeatures.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **toggle_feature_for_project**
> ContainerForProjectFeatures toggle_feature_for_project(body, project_id_or_key, feature_key)

Set project feature state

Sets the state of a project feature.

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
api_instance = jira_client.ProjectFeaturesApi(jira_client.ApiClient(configuration))
body = jira_client.ProjectFeatureState() # ProjectFeatureState | Details of the feature state change.
project_id_or_key = 'project_id_or_key_example' # str | The ID or (case-sensitive) key of the project.
feature_key = 'feature_key_example' # str | The key of the feature.

try:
    # Set project feature state
    api_response = api_instance.toggle_feature_for_project(body, project_id_or_key, feature_key)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling ProjectFeaturesApi->toggle_feature_for_project: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**ProjectFeatureState**](ProjectFeatureState.md)| Details of the feature state change. | 
 **project_id_or_key** | **str**| The ID or (case-sensitive) key of the project. | 
 **feature_key** | **str**| The key of the feature. | 

### Return type

[**ContainerForProjectFeatures**](ContainerForProjectFeatures.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

