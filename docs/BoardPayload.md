# BoardPayload

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**board_filter_jql** | **str** | Takes in a JQL string to create a new filter. If no value is provided, it&#x27;ll default to a JQL filter for the project creating | [optional] 
**card_color_strategy** | **str** | Card color settings of the board | [optional] 
**card_layout** | [**CardLayout**](CardLayout.md) |  | [optional] 
**card_layouts** | [**list[CardLayoutField]**](CardLayoutField.md) | Card layout settings of the board | [optional] 
**columns** | [**list[BoardColumnPayload]**](BoardColumnPayload.md) | The columns of the board | [optional] 
**features** | [**list[BoardFeaturePayload]**](BoardFeaturePayload.md) | Feature settings for the board | [optional] 
**name** | **str** | The name of the board | [optional] 
**pcri** | [**ProjectCreateResourceIdentifier**](ProjectCreateResourceIdentifier.md) |  | [optional] 
**quick_filters** | [**list[QuickFilterPayload]**](QuickFilterPayload.md) | The quick filters for the board. | [optional] 
**supports_sprint** | **bool** | Whether sprints are supported on the board | [optional] [default to True]
**swimlanes** | [**SwimlanesPayload**](SwimlanesPayload.md) |  | [optional] 
**working_days_config** | [**WorkingDaysConfig**](WorkingDaysConfig.md) |  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

