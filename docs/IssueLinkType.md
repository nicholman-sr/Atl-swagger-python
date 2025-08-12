# IssueLinkType

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | The ID of the issue link type and is used as follows:   *  In the [ issueLink](#api-rest-api-3-issueLink-post) resource it is the type of issue link. Required on create when &#x60;name&#x60; isn&#x27;t provided. Otherwise, read only.  *  In the [ issueLinkType](#api-rest-api-3-issueLinkType-post) resource it is read only. | [optional] 
**inward** | **str** | The description of the issue link type inward link and is used as follows:   *  In the [ issueLink](#api-rest-api-3-issueLink-post) resource it is read only.  *  In the [ issueLinkType](#api-rest-api-3-issueLinkType-post) resource it is required on create and optional on update. Otherwise, read only. | [optional] 
**name** | **str** | The name of the issue link type and is used as follows:   *  In the [ issueLink](#api-rest-api-3-issueLink-post) resource it is the type of issue link. Required on create when &#x60;id&#x60; isn&#x27;t provided. Otherwise, read only.  *  In the [ issueLinkType](#api-rest-api-3-issueLinkType-post) resource it is required on create and optional on update. Otherwise, read only. | [optional] 
**outward** | **str** | The description of the issue link type outward link and is used as follows:   *  In the [ issueLink](#api-rest-api-3-issueLink-post) resource it is read only.  *  In the [ issueLinkType](#api-rest-api-3-issueLinkType-post) resource it is required on create and optional on update. Otherwise, read only. | [optional] 
**_self** | **str** | The URL of the issue link type. Read only. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

