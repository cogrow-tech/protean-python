# CreateSemanticChunksResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**chunks** | [**List[Chunk]**](Chunk.md) | The chunks of text. | [optional] 
**model_id** | **str** |  | [optional] 
**threshold** | **float** | The threshold value used to create breakpoints. This calculated based on breakpointStrategy and breakpointThresholdTuner from the request. | [optional] 
**breakpoints** | **List[int]** | The breakpoints created where distance/gradient &gt;&#x3D; threshold value. | [optional] 
**sentences** | [**List[Sentence]**](Sentence.md) | The sentences used to create chunks. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


