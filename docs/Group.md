# Group

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**expand** | **str** | Expand options that include additional group details in the response. | [optional] 
**group_id** | **str** | The ID of the group, which uniquely identifies the group across all Atlassian products. For example, *952d12c3-5b5b-4d04-bb32-44d383afc4b2*. | [optional] 
**name** | **str** | The name of group. | [optional] 
**_self** | **str** | The URL for these group details. | [optional] 
**users** | **AllOfGroupUsers** | A paginated list of the users that are members of the group. A maximum of 50 users is returned in the list, to access additional users append &#x60;[start-index:end-index]&#x60; to the expand request. For example, to access the next 50 users, use&#x60;?expand&#x3D;users[51:100]&#x60;. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

