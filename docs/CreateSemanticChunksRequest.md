# CreateSemanticChunksRequest

Configuration parameters that define how chunking is applied.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **str** | The text to chunk. This must be provided if file is not being uploaded. | [optional] 
**embedding_model** | **str** | The embedding model to use for chunking. If no value is provided then default embedding model of Protean platform is used. | [optional] 
**text_splitting_strategy** | [**TextSplittingStrategy**](TextSplittingStrategy.md) | Semantic chunking splits text into sentences, which are later combined. This property determines how input text is split into sentences. | [optional] 
**combining_strategy** | [**CombiningStrategy**](CombiningStrategy.md) | Semantic chunking combines multiple sentences and then uses this combined unit for similarity comparison. This property determines how sentences are combined to form a unit for comparison. | [optional] 
**buffer_size** | **int** | This property determines how many sentences are combined using CombiningStrategy. | [optional] 
**similarity_strategy** | [**SimilarityStrategy**](SimilarityStrategy.md) | Semantic chunking calculates distance scores between subsequent combined units to measure how much the meaning shifts from one to the next, helping identify where the content becomes less cohesive. This property determines how to calculate similarity-score and distance to subsequent unit. | [optional] 
**breakpoint_strategy** | [**BreakpointStrategy**](BreakpointStrategy.md) | Semantic chunking uses distance scores to determine the optimal boundaries between combined units. This property defines the method for analyzing those distance values to decide where meaningful breaks in the content should occur. | [optional] 
**breakpoint_threshold_tuner** | **float** | This property controls how sensitive the BreakpointStrategy is when identifying where to break the text into chunks. It determines what constitutes a &#39;significant enough&#39; change or low enough similarity to qualify as a semantic boundary. Increase breakpointThresholdTuner to reduce splits (larger chunks). Decrease it to get more splits, (smaller chunks). Default Values: PERCENTILE - 85.0;  STANDARD_DEVIATION - 3.0; INTERQUARTILE - 0.05; GRADIENT - 95.0  | [optional] 
**maximum_chunk_size** | **int** | After semantic chunking, if the resulting chunk sizes are too big, the chunks will be broken further. This determines the number of tokes after which a chunk will be split.  It attempts to find a suitable break point (&#39;.&#39;, &#39;!&#39; and &#39;?&#39;) | [optional] [default to 800]
**generate_embeddings** | **bool** | Whether to generate and return embeddings. | [optional] [default to False]
**metadata** | **Dict[str, object]** | The &lt;key,value&gt; pairs which are used to annotate the document. This could be used in full text search or similarity search. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


