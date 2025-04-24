# DatasetSearchRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **str** | The query to search for relevant data in the datasets. | [optional] 
**limit** | **int** | The maximum number of dataset chunks to return for the provided query. | [optional] [default to 3]
**dataset_ids** | **List[str]** | The dataset IDs to run the query against. Expected values are either dataset GUID or *, where * will use all datasets that you are authorized for. | [optional] 
**score_threshold** | **float** | Cut off point for the relevance of dataset chunks to the provided user_message. Higher value implies higher level of relevance of the dataset chunks to the provided user_message. | [optional] [default to 0.0]
**search_type** | [**DatasetSearchType**](DatasetSearchType.md) | Select the search type to use between full-text, similarity or hybrid which combines results full-text and similarity using Reciprocal Rank Fusion (RRF). | [optional] 
**use_reranker** | **bool** | Enable reranking the results of searches using advanced language models to improve relevance. After the initial retrieval (e.g., via full-text or vector search), results are re-scored based on semantic closeness to the query to get contextually accurate matches. | [optional] [default to True]
**filter_expression** | **str** | An optional filter expression used to narrow down the search results based on document metadata fields. Expressions can include logical operators like AND, OR, grouping with parentheses, and comparison operators such as &#x3D;&#x3D;, !&#x3D;, &gt;&#x3D;, &lt;&#x3D;, IN, and NOT IN. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


