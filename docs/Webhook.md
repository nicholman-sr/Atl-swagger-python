# Webhook

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**events** | **list[str]** | The Jira events that trigger the webhook. | 
**expiration_date** | **int** | The date after which the webhook is no longer sent. Use [Extend webhook life](https://developer.atlassian.com/cloud/jira/platform/rest/v3/api-group-webhooks/#api-rest-api-3-webhook-refresh-put) to extend the date. | [optional] 
**field_ids_filter** | **list[str]** | A list of field IDs. When the issue changelog contains any of the fields, the webhook &#x60;jira:issue_updated&#x60; is sent. If this parameter is not present, the app is notified about all field updates. | [optional] 
**id** | **int** | The ID of the webhook. | 
**issue_property_keys_filter** | **list[str]** | A list of issue property keys. A change of those issue properties triggers the &#x60;issue_property_set&#x60; or &#x60;issue_property_deleted&#x60; webhooks. If this parameter is not present, the app is notified about all issue property updates. | [optional] 
**jql_filter** | **str** | The JQL filter that specifies which issues the webhook is sent for. | 
**url** | **str** | The URL that specifies where the webhooks are sent. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

