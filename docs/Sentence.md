# Sentence


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | **int** | The position of sentence in the original text. Starts at 0. | [optional] 
**content** | **str** | The original text of the sentence. | [optional] 
**combined** | **str** | The combined text if this sentence was merged with others using CombiningStrategy. | [optional] 
**distance_to_next** | **float** | The semantic distance to the next sentence&#39; &#x60;embedding&#x60; property. | [optional] 
**gradient** | **float** | The change in &#x60;distanceToNext&#x60; property between this and the next sentence pair. | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


