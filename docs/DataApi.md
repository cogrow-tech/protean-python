# DataApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_fixed_size_chunks**](DataApi.md#create_fixed_size_chunks) | **POST** /api/data-service/data/transformation/chunk/fixed-size | Splits text into chunks based on token count.
[**create_semantic_chunks**](DataApi.md#create_semantic_chunks) | **POST** /api/data-service/data/transformation/chunk/semantic | Splits text into chunks that are semantically similar.


# **create_fixed_size_chunks**

This will perform chunking based on token count.
It attempts to find a suitable break point ('.', '!' and '?', or '\n').
If a break point is found, it truncates the chunk at that point.



### Parameters
Input examples could be found [here](DataApiExamples.md#create_fixed_size_chunks).


Name | Type | Notes
------------- | ------------- | -------------
 **create_fixed_size_chunks_request** | [**CreateFixedSizeChunksRequest**](CreateFixedSizeChunksRequest.md) | 

### Return type

[**CreateFixedSizeChunksResponse**](CreateFixedSizeChunksResponse.md)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_semantic_chunks**

This will performs semantic chunking by analyzing a text input and segmenting it into coherent units based on meaning rather than syntax alone.
It could use NLP techniques to identify sentences that will handle urls, emails etc.
NLP techniques only work with 'english', for other languages it identifies sentences based on '.', '!' and '?'.


### Parameters
Input examples could be found [here](DataApiExamples.md#create_semantic_chunks).


Name | Type | Notes
------------- | ------------- | -------------
 **create_semantic_chunks_request** | [**CreateSemanticChunksRequest**](CreateSemanticChunksRequest.md) | 
 **include_explanation** | **bool** | [optional] [default to False]

### Return type

[**CreateSemanticChunksResponse**](CreateSemanticChunksResponse.md)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | OK |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

