# VectorSearchRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**query** | **str** | The query to search against the vector datasets. | [optional] 
**limit** | **int** | The maximum number of dataset chunks to return for the provided query. | [optional] [default to 3]
**resource_ids** | **List[str]** | The dataset IDs to run the query against. | [optional] 
**relevance_threshold** | **float** | Cut off point for the relevance of dataset chunks to the provided user_message. Higher value implies higher level of relevance of the dataset chunks to the provided user_message. | [optional] [default to 0.8]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


