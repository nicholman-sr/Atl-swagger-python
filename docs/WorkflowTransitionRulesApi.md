# jira_client.WorkflowTransitionRulesApi

All URIs are relative to *https://your-domain.atlassian.net*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_workflow_transition_rule_configurations**](WorkflowTransitionRulesApi.md#delete_workflow_transition_rule_configurations) | **PUT** /rest/api/3/workflow/rule/config/delete | Delete workflow transition rule configurations
[**get_workflow_transition_rule_configurations**](WorkflowTransitionRulesApi.md#get_workflow_transition_rule_configurations) | **GET** /rest/api/3/workflow/rule/config | Get workflow transition rule configurations
[**update_workflow_transition_rule_configurations**](WorkflowTransitionRulesApi.md#update_workflow_transition_rule_configurations) | **PUT** /rest/api/3/workflow/rule/config | Update workflow transition rule configurations

# **delete_workflow_transition_rule_configurations**
> WorkflowTransitionRulesUpdateErrors delete_workflow_transition_rule_configurations(body)

Delete workflow transition rule configurations

Deletes workflow transition rules from one or more workflows. These rule types are supported:   *  [post functions](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-post-function/)  *  [conditions](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-condition/)  *  [validators](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-validator/)  Only rules created by the calling Connect app can be deleted.  **[Permissions](#permissions) required:** Only Connect apps can use this operation.

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
api_instance = jira_client.WorkflowTransitionRulesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowsWithTransitionRulesDetails() # WorkflowsWithTransitionRulesDetails | 

try:
    # Delete workflow transition rule configurations
    api_response = api_instance.delete_workflow_transition_rule_configurations(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowTransitionRulesApi->delete_workflow_transition_rule_configurations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowsWithTransitionRulesDetails**](WorkflowsWithTransitionRulesDetails.md)|  | 

### Return type

[**WorkflowTransitionRulesUpdateErrors**](WorkflowTransitionRulesUpdateErrors.md)

### Authorization

[basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_workflow_transition_rule_configurations**
> PageBeanWorkflowTransitionRules get_workflow_transition_rule_configurations(types, start_at=start_at, max_results=max_results, keys=keys, workflow_names=workflow_names, with_tags=with_tags, draft=draft, expand=expand)

Get workflow transition rule configurations

Returns a [paginated](#pagination) list of workflows with transition rules. The workflows can be filtered to return only those containing workflow transition rules:   *  of one or more transition rule types, such as [workflow post functions](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-post-function/).  *  matching one or more transition rule keys.  Only workflows containing transition rules created by the calling [Connect](https://developer.atlassian.com/cloud/jira/platform/index/#connect-apps) or [Forge](https://developer.atlassian.com/cloud/jira/platform/index/#forge-apps) app are returned.  Due to server-side optimizations, workflows with an empty list of rules may be returned; these workflows can be ignored.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/index/#connect-apps) or [Forge](https://developer.atlassian.com/cloud/jira/platform/index/#forge-apps) apps can use this operation.

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
api_instance = jira_client.WorkflowTransitionRulesApi(jira_client.ApiClient(configuration))
types = ['types_example'] # list[str] | The types of the transition rules to return.
start_at = 0 # int | The index of the first item to return in a page of results (page offset). (optional) (default to 0)
max_results = 10 # int | The maximum number of items to return per page. (optional) (default to 10)
keys = ['keys_example'] # list[str] | The transition rule class keys, as defined in the Connect or the Forge app descriptor, of the transition rules to return. (optional)
workflow_names = ['workflow_names_example'] # list[str] | The list of workflow names to filter by. (optional)
with_tags = ['with_tags_example'] # list[str] | The list of `tags` to filter by. (optional)
draft = true # bool | Whether draft or published workflows are returned. If not provided, both workflow types are returned. (optional)
expand = 'expand_example' # str | Use [expand](#expansion) to include additional information in the response. This parameter accepts `transition`, which, for each rule, returns information about the transition the rule is assigned to. (optional)

try:
    # Get workflow transition rule configurations
    api_response = api_instance.get_workflow_transition_rule_configurations(types, start_at=start_at, max_results=max_results, keys=keys, workflow_names=workflow_names, with_tags=with_tags, draft=draft, expand=expand)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowTransitionRulesApi->get_workflow_transition_rule_configurations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **types** | [**list[str]**](str.md)| The types of the transition rules to return. | 
 **start_at** | **int**| The index of the first item to return in a page of results (page offset). | [optional] [default to 0]
 **max_results** | **int**| The maximum number of items to return per page. | [optional] [default to 10]
 **keys** | [**list[str]**](str.md)| The transition rule class keys, as defined in the Connect or the Forge app descriptor, of the transition rules to return. | [optional] 
 **workflow_names** | [**list[str]**](str.md)| The list of workflow names to filter by. | [optional] 
 **with_tags** | [**list[str]**](str.md)| The list of &#x60;tags&#x60; to filter by. | [optional] 
 **draft** | **bool**| Whether draft or published workflows are returned. If not provided, both workflow types are returned. | [optional] 
 **expand** | **str**| Use [expand](#expansion) to include additional information in the response. This parameter accepts &#x60;transition&#x60;, which, for each rule, returns information about the transition the rule is assigned to. | [optional] 

### Return type

[**PageBeanWorkflowTransitionRules**](PageBeanWorkflowTransitionRules.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_workflow_transition_rule_configurations**
> WorkflowTransitionRulesUpdateErrors update_workflow_transition_rule_configurations(body)

Update workflow transition rule configurations

Updates configuration of workflow transition rules. The following rule types are supported:   *  [post functions](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-post-function/)  *  [conditions](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-condition/)  *  [validators](https://developer.atlassian.com/cloud/jira/platform/modules/workflow-validator/)  Only rules created by the calling [Connect](https://developer.atlassian.com/cloud/jira/platform/index/#connect-apps) or [Forge](https://developer.atlassian.com/cloud/jira/platform/index/#forge-apps) app can be updated.  To assist with app migration, this operation can be used to:   *  Disable a rule.  *  Add a `tag`. Use this to filter rules in the [Get workflow transition rule configurations](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-workflow-transition-rules/#api-rest-api-3-workflow-rule-config-get).  Rules are enabled if the `disabled` parameter is not provided.  **[Permissions](#permissions) required:** Only [Connect](https://developer.atlassian.com/cloud/jira/platform/index/#connect-apps) or [Forge](https://developer.atlassian.com/cloud/jira/platform/index/#forge-apps) apps can use this operation.

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
api_instance = jira_client.WorkflowTransitionRulesApi(jira_client.ApiClient(configuration))
body = jira_client.WorkflowTransitionRulesUpdate() # WorkflowTransitionRulesUpdate | 

try:
    # Update workflow transition rule configurations
    api_response = api_instance.update_workflow_transition_rule_configurations(body)
    pprint(api_response)
except ApiException as e:
    print("Exception when calling WorkflowTransitionRulesApi->update_workflow_transition_rule_configurations: %s\n" % e)
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**WorkflowTransitionRulesUpdate**](WorkflowTransitionRulesUpdate.md)|  | 

### Return type

[**WorkflowTransitionRulesUpdateErrors**](WorkflowTransitionRulesUpdateErrors.md)

### Authorization

[OAuth2](../README.md#OAuth2), [basicAuth](../README.md#basicAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

