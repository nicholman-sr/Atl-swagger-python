# RedactionPosition

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**adf_pointer** | **str** | The ADF pointer indicating the position of the text to be redacted. This is only required when redacting from rich text(ADF) fields. For plain text fields, this field can be omitted. | [optional] 
**expected_text** | **str** | The text which will be redacted, encoded using SHA256 hash and Base64 digest | 
**_from** | **int** | The start index(inclusive) for the redaction in specified content | 
**to** | **int** | The ending index(exclusive) for the redaction in specified content | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)

