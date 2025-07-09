# ConvertFileToMdRequest

Configuration to control conversion of file

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**include_images** | **bool** | If enabled, images will be extracted from the document. | [optional] [default to False]
**table_processing_mode** | [**TableProcessingMode**](TableProcessingMode.md) | Mode to use when extracting table structure from the file. Consider using &#x60;FAST&#x60; if table structure is not very complex as it would decrease processing time. Should be &#x60;DISABLED&#x60; if not needed as it takes considerable amount of time to process.  | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


