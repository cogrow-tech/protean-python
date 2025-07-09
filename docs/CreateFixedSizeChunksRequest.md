# CreateFixedSizeChunksRequest

Configuration parameters that define how chunking is applied. Fixed size chunking is used if none is provided.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **str** | The text to chunk. This must be provided if file is not being uploaded. | [optional] 
**chunk_size** | **int** | The target size of each text chunk in tokens. | [optional] [default to 800]
**min_chunk_size_chars** | **int** | The minimum size of each text chunk in characters. | [optional] [default to 350]
**min_chunk_length_to_embed** | **int** | The minimum length of a chunk to be included. | [optional] [default to 5]
**max_num_chunks** | **int** | The maximum number of chunks to generate from a text. | [optional] [default to 10000]
**keep_separator** | **bool** | Whether to keep separators (like newlines) in the chunks. | [optional] [default to True]
**generate_embeddings** | **bool** | Whether to generate and return embeddings. | [optional] [default to False]
**embedding_model** | **str** | The embedding model to use for chunking. If no value is provided then default embedding model of Protean platform is used. | [optional] 
**metadata** | **Dict[str, object]** | The &lt;key,value&gt; pairs which are used to annotate the document. This could be used in full text search or similarity search. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


