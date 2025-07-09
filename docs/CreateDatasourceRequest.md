# CreateDatasourceRequest

Configuration to control processing of file. Provide one of fixedSizeChunking, semanticChunking or lateChunking

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**fixed_size_chunking** | [**CreateFixedSizeChunksRequest**](CreateFixedSizeChunksRequest.md) | Configuration parameters that define how chunking is applied. Fixed size chunking is used if none is provided. | [optional] 
**sematic_chunking** | [**CreateSemanticChunksRequest**](CreateSemanticChunksRequest.md) | Configuration parameters that define how chunking is applied. | [optional] 
**late_chunking** | [**CreateLateChunksRequest**](CreateLateChunksRequest.md) | Configuration parameters that define how chunking is applied. | [optional] 
**datasource_name** | **str** | Human-readable name of the datasource from which the document originates. Used for tracking, display, and reference purposes. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


