# FoundGroup

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**avatar_url** | **str** | Avatar url for the group/team if present. | [optional] 
**group_id** | **str** | The ID of the group, which uniquely identifies the group across all Atlassian products. For example, *952d12c3-5b5b-4d04-bb32-44d383afc4b2*. | [optional] 
**html** | **str** | The group name with the matched query string highlighted with the HTML bold tag. | [optional] 
**labels** | [**list[GroupLabel]**](GroupLabel.md) |  | [optional] 
**managed_by** | **str** | Describes who/how the team is managed. The possible values are   \\* external - when team is synced from an external directory like SCIM or HRIS, and team members cannot be modified.   \\* admins - when a team is managed by an admin (team members can only be modified by admins).   \\* team-members - managed by existing team members, new members need to be invited to join.   \\* open - anyone can join or modify this team. | [optional] 
**name** | **str** | The name of the group. The name of a group is mutable, to reliably identify a group use &#x60;&#x60;groupId&#x60;.&#x60; | [optional] 
**usage_type** | **str** | Describes the type of group. The possible values are   \\* team-collaboration - A platform team managed in people directory.   \\* userbase-group - a group of users created in adminhub.   \\* admin-oversight - currently unused. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

