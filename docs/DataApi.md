# DataApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**convert_file_to_markdown**](DataApi.md#convert_file_to_markdown) | **POST** /api/data-service/data/extract/file/convert-to-md | Convert file content into markdown.
[**create_embeddings**](DataApi.md#create_embeddings) | **POST** /api/data-service/data/embed | Creates embeddings for texts.
[**create_fixed_size_chunks_from_file**](DataApi.md#create_fixed_size_chunks_from_file) | **POST** /api/data-service/data/chunk/file/fixed-size | Splits file contents into chunks based on token count.
[**create_fixed_size_chunks_from_text**](DataApi.md#create_fixed_size_chunks_from_text) | **POST** /api/data-service/data/chunk/text/fixed-size | Splits text into chunks based on token count.
[**create_late_chunks_from_file**](DataApi.md#create_late_chunks_from_file) | **POST** /api/data-service/data/chunk/file/late | Splits contents of file into chunks using late chunking technique. The model being used to perform chunking must have pooling&#x3D;&#39;none&#39;
[**create_late_chunks_from_text**](DataApi.md#create_late_chunks_from_text) | **POST** /api/data-service/data/chunk/text/late | 
[**create_semantic_chunks_from_file**](DataApi.md#create_semantic_chunks_from_file) | **POST** /api/data-service/data/chunk/file/semantic | Splits contents of file into chunks that are semantically similar.
[**create_semantic_chunks_from_text**](DataApi.md#create_semantic_chunks_from_text) | **POST** /api/data-service/data/chunk/text/semantic | Splits text into chunks that are semantically similar.


# **convert_file_to_markdown**

Parse file content and convert it into markdown format.
Service employs combination of OCR and a set of specialized models to perform accurate data extraction.
Supported file formats are: pdf,docx,pptx,xlsx,html,csv.



### Parameters
Input examples could be found [here](DataApiExamples.md#convert_file_to_markdown).


Name | Type | Notes
------------- | ------------- | -------------
 **file** | **bytearray** | 
 **convert_file_to_md_request** | [**ConvertFileToMdRequest**](ConvertFileToMdRequest.md) | 

### Return type

[**ConvertFileToMdResponse**](ConvertFileToMdResponse.md)

### HTTP request headers

 - **Content-Type**: multipart/form-data
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

# **create_embeddings**

This will generate embeddings using the specified model. If no model is provided, the default embedding model will be used.
Ensure the model's pooling strategy is set to 'none' when late chunking is enabled..



### Parameters
Input examples could be found [here](DataApiExamples.md#create_embeddings).


Name | Type | Notes
------------- | ------------- | -------------
 **create_embeddings_request** | [**CreateEmbeddingsRequest**](CreateEmbeddingsRequest.md) | 

### Return type

[**CreateEmbeddingsResponse**](CreateEmbeddingsResponse.md)

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

# **create_fixed_size_chunks_from_file**

This will perform chunking on file contents based on token count.
It attempts to find a suitable break point ('.', '!' and '?', or '\n').
If a break point is found, it truncates the chunk at that point.



### Parameters
Input examples could be found [here](DataApiExamples.md#create_fixed_size_chunks_from_file).


Name | Type | Notes
------------- | ------------- | -------------
 **file** | **bytearray** | 
 **create_fixed_size_chunks_request** | [**CreateFixedSizeChunksRequest**](CreateFixedSizeChunksRequest.md) | [optional] 

### Return type

[**CreateFixedSizeChunksResponse**](CreateFixedSizeChunksResponse.md)

### HTTP request headers

 - **Content-Type**: multipart/form-data
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

# **create_fixed_size_chunks_from_text**

This will perform chunking based on token count.
It attempts to find a suitable break point ('.', '!' and '?', or '\n').
If a break point is found, it truncates the chunk at that point.



### Parameters
Input examples could be found [here](DataApiExamples.md#create_fixed_size_chunks_from_text).


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

# **create_late_chunks_from_file**

This will performs late chunking by reading content of file and segmenting it into coherent units using late chunking technique.
It could use NLP techniques to identify sentences that will handle urls, emails etc.
NLP techniques only work with 'english', for other languages it identifies sentences based on '.', '!' and '?'.


### Parameters
Input examples could be found [here](DataApiExamples.md#create_late_chunks_from_file).


Name | Type | Notes
------------- | ------------- | -------------
 **file** | **bytearray** | 
 **create_late_chunks_request** | [**CreateLateChunksRequest**](CreateLateChunksRequest.md) | [optional] 

### Return type

[**CreateLateChunksResponse**](CreateLateChunksResponse.md)

### HTTP request headers

 - **Content-Type**: multipart/form-data
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

# **create_late_chunks_from_text**


### Parameters
Input examples could be found [here](DataApiExamples.md#create_late_chunks_from_text).


Name | Type | Notes
------------- | ------------- | -------------
 **create_late_chunks_request** | [**CreateLateChunksRequest**](CreateLateChunksRequest.md) | 

### Return type

[**CreateLateChunksResponse**](CreateLateChunksResponse.md)

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

# **create_semantic_chunks_from_file**

This will performs semantic chunking by analyzing content of file and segmenting it into coherent units based on meaning rather than syntax alone.
It could use NLP techniques to identify sentences that will handle urls, emails etc.
NLP techniques only work with 'english', for other languages it identifies sentences based on '.', '!' and '?'.


### Parameters
Input examples could be found [here](DataApiExamples.md#create_semantic_chunks_from_file).


Name | Type | Notes
------------- | ------------- | -------------
 **file** | **bytearray** | 
 **include_explanation** | **bool** | [optional] [default to False]
 **create_semantic_chunks_request** | [**CreateSemanticChunksRequest**](CreateSemanticChunksRequest.md) | [optional] 

### Return type

[**CreateSemanticChunksResponse**](CreateSemanticChunksResponse.md)

### HTTP request headers

 - **Content-Type**: multipart/form-data
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

# **create_semantic_chunks_from_text**

This will performs semantic chunking by analyzing a text input and segmenting it into coherent units based on meaning rather than syntax alone.
It could use NLP techniques to identify sentences that will handle urls, emails etc.
NLP techniques only work with 'english', for other languages it identifies sentences based on '.', '!' and '?'.


### Parameters
Input examples could be found [here](DataApiExamples.md#create_semantic_chunks_from_text).


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

