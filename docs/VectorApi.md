# VectorApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**search**](VectorApi.md#search) | **POST** /api/vector-service/vectors/search | Search in vector store


# **search**

Search for vector documents that closely match provided query. Service utilizes both hybrid search
and reranking to retrieve the best possible match.


### Parameters
Input examples could be found [here](VectorApiExamples.md#search).


Name | Type | Notes
------------- | ------------- | -------------
 **vector_search_request** | [**VectorSearchRequest**](VectorSearchRequest.md) | 

### Return type

[**VectorSearchResponse**](VectorSearchResponse.md)

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

