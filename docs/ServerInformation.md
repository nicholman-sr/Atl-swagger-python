# ServerInformation

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**base_url** | **str** | The base URL of the Jira instance. | [optional] 
**build_date** | **datetime** | The timestamp when the Jira version was built. | [optional] 
**build_number** | **int** | The build number of the Jira version. | [optional] 
**deployment_type** | **str** | The type of server deployment. This is always returned as *Cloud*. | [optional] 
**display_url** | **str** | The display URL of the Jira instance. | [optional] 
**display_url_confluence** | **str** | The display URL of Confluence. | [optional] 
**display_url_servicedesk_help_center** | **str** | The display URL of the Servicedesk Help Center. | [optional] 
**health_checks** | [**list[HealthCheckResult]**](HealthCheckResult.md) | Jira instance health check results. Deprecated and no longer returned. | [optional] 
**scm_info** | **str** | The unique identifier of the Jira version. | [optional] 
**server_time** | **datetime** | The time in Jira when this request was responded to. | [optional] 
**server_time_zone** | **str** | The default timezone of the Jira server. In a format known as Olson Time Zones, IANA Time Zones or TZ Database Time Zones. | [optional] 
**server_title** | **str** | The name of the Jira instance. | [optional] 
**version** | **str** | The version of Jira. | [optional] 
**version_numbers** | **list[int]** | The major, minor, and revision version numbers of the Jira version. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

