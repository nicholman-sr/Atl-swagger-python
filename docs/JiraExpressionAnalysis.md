# JiraExpressionAnalysis

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**complexity** | [**JiraExpressionComplexity**](JiraExpressionComplexity.md) |  | [optional] 
**errors** | [**list[JiraExpressionValidationError]**](JiraExpressionValidationError.md) | A list of validation errors. Not included if the expression is valid. | [optional] 
**expression** | **str** | The analysed expression. | 
**type** | **str** | EXPERIMENTAL. The inferred type of the expression. | [optional] 
**valid** | **bool** | Whether the expression is valid and the interpreter will evaluate it. Note that the expression may fail at runtime (for example, if it executes too many expensive operations). | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

