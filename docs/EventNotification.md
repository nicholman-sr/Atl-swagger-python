# EventNotification

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**email_address** | **str** | The email address. | [optional] 
**expand** | **str** | Expand options that include additional event notification details in the response. | [optional] 
**field** | **AllOfEventNotificationField** | The custom user or group field. | [optional] 
**group** | **AllOfEventNotificationGroup** | The specified group. | [optional] 
**id** | **int** | The ID of the notification. | [optional] 
**notification_type** | **str** | Identifies the recipients of the notification. | [optional] 
**parameter** | **str** | As a group&#x27;s name can change, use of &#x60;recipient&#x60; is recommended. The identifier associated with the &#x60;notificationType&#x60; value that defines the receiver of the notification, where the receiver isn&#x27;t implied by &#x60;notificationType&#x60; value. So, when &#x60;notificationType&#x60; is:   *  &#x60;User&#x60; The &#x60;parameter&#x60; is the user account ID.  *  &#x60;Group&#x60; The &#x60;parameter&#x60; is the group name.  *  &#x60;ProjectRole&#x60; The &#x60;parameter&#x60; is the project role ID.  *  &#x60;UserCustomField&#x60; The &#x60;parameter&#x60; is the ID of the custom field.  *  &#x60;GroupCustomField&#x60; The &#x60;parameter&#x60; is the ID of the custom field. | [optional] 
**project_role** | **AllOfEventNotificationProjectRole** | The specified project role. | [optional] 
**recipient** | **str** | The identifier associated with the &#x60;notificationType&#x60; value that defines the receiver of the notification, where the receiver isn&#x27;t implied by the &#x60;notificationType&#x60; value. So, when &#x60;notificationType&#x60; is:   *  &#x60;User&#x60;, &#x60;recipient&#x60; is the user account ID.  *  &#x60;Group&#x60;, &#x60;recipient&#x60; is the group ID.  *  &#x60;ProjectRole&#x60;, &#x60;recipient&#x60; is the project role ID.  *  &#x60;UserCustomField&#x60;, &#x60;recipient&#x60; is the ID of the custom field.  *  &#x60;GroupCustomField&#x60;, &#x60;recipient&#x60; is the ID of the custom field. | [optional] 
**user** | **AllOfEventNotificationUser** | The specified user. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

