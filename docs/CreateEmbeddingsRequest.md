# CreateEmbeddingsRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**texts** | **List[str]** | Collection of input texts to generate embeddings for. | 
**is_late_chunked** | **bool** | Whether to apply late chunking to the input text. If set to true, ensure that the modelId refers to an embedding model with pooling strategy set to &#39;none&#39;. | [optional] [default to False]
**model_id** | **str** | The embedding model to use to generate embedding. If no value is provided then default embedding model is used. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


