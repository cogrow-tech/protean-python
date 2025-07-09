# CreateDatasourceFromChunksRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**documents** | [**List[ProteanDocument]**](ProteanDocument.md) | Collection of text chunks for which embeddings will be generated and stored as documents in the datasource. | 
**model_id** | **str** | Identifies the model that will be used to generate embeddings. | [optional] 
**datasource_name** | **str** | Name to assign to the automatically created datasource. | 
**embed_metadata** | **bool** | Indicates whether metadata key-value pairs should be embedded into the stored content and generated vectors to enhance the retrieval process.  | [optional] [default to True]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


