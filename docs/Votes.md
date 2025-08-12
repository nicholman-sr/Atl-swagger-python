# Votes

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**has_voted** | **bool** | Whether the user making this request has voted on the issue. | [optional] 
**_self** | **str** | The URL of these issue vote details. | [optional] 
**voters** | [**list[User]**](User.md) | List of the users who have voted on this issue. An empty list is returned when the calling user doesn&#x27;t have the *View voters and watchers* project permission. | [optional] 
**votes** | **int** | The number of votes on the issue. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

