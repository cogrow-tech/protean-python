# CreateLateChunksRequest

Configuration parameters that define how chunking is applied.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **str** | The text to chunk. This must be provided if file is not being uploaded. | [optional] 
**embedding_model** | **str** | The embedding model to use for chunking. If no value is provided then default embedding model of Protean platform is used. | [optional] 
**text_splitting_strategy** | [**TextSplittingStrategy**](TextSplittingStrategy.md) | ..... | [optional] 
**chunk_size** | **int** | This determines the number of tokens after which a chunk will be split. It attempts to find a suitable break point (&#39;.&#39;, &#39;!&#39; and &#39;?&#39;) | [optional] [default to 800]
**overlap_percentage** | **int** | This determines the amount of overlap across macro chunks in terms of percentage | [optional] [default to 10]
**metadata** | **Dict[str, object]** | The &lt;key,value&gt; pairs which are used to annotate the document. This could be used in full text search or similarity search. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


