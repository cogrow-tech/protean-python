# ChatQuestionRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**model** | **str** | ID of the model to use when generating the response. | 
**system_message** | **str** | The system message to use when generating the response. | 
**user_message** | **str** | The user prompt to generate response for. | 
**temperature** | **float** | Affects the level of creativity that should be applied when generating response. Accepts values from 0.0 to 1.0 where higher value implies higher level of creativity applied during generation. | [optional] [default to 0.4]
**datasets** | **List[str]** | The datasets to be used for RAG purposes during generation. Expected values are either dataset GUID or &#39;*&#39;, where &#39;*&#39; implies to use all datasets that are available to you. | [optional] 
**limit** | **int** | The maximum number of dataset chunks to include into the context during generation. | [optional] [default to 3]
**relevance_threshold** | **float** | Cut off point for the relevance of dataset chunks to the provided user_message. Higher value implies higher level of relevance of the dataset chunks to the provided user_message. | [optional] [default to 0.8]
**assistant_id** | **str** | The assistant ID to use when generating the response. | [optional] 
**client_tools** | [**ClientTools**](ClientTools.md) | List of functions the model may generate JSON inputs for. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


