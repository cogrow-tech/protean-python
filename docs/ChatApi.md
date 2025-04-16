# ChatApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**question**](ChatApi.md#question) | **POST** /api/chat-service/question | RAG enabled text completion.


# **question**

Generate RAG enabled model response for the provided prompt.


### Parameters
Input examples could be found [here](ChatApiExamples.md#question).


Name | Type | Notes
------------- | ------------- | -------------
 **chat_question_request** | [**ChatQuestionRequest**](ChatQuestionRequest.md) | 

### Return type

[**ChatQuestionResponse**](ChatQuestionResponse.md)

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

