# DatasetApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_dataset**](DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
[**create_documents_in_dataset**](DatasetApi.md#create_documents_in_dataset) | **POST** /api/dataset-service/datasets/{id}/datasources/documents | Create documents in the dataset.
[**create_documents_in_datasource**](DatasetApi.md#create_documents_in_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Create documents in the datasource.
[**create_file_datasource**](DatasetApi.md#create_file_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources/file | Create file datasource in the dataset.
[**delete_dataset**](DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{id} | Delete dataset.
[**delete_datasource**](DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId} | Delete datasource from the dataset.
[**delete_documents_by_document_ids**](DatasetApi.md#delete_documents_by_document_ids) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Delete documents in the datasource of the dataset.
[**get_dataset**](DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{id} | Get dataset.
[**get_datasets**](DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get datasets.
[**get_documents**](DatasetApi.md#get_documents) | **GET** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Get documents in the datasource of the dataset.
[**search**](DatasetApi.md#search) | **POST** /api/dataset-service/datasets/search | Search in dataset(s).
[**update_dataset**](DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{id} | Update dataset.
[**update_documents**](DatasetApi.md#update_documents) | **PUT** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Update documents in the datasource of the dataset.


# **create_dataset**

Create dataset to aggregate and manage authorizations across multiple datasources.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **create_dataset_request** | [**CreateDatasetRequest**](CreateDatasetRequest.md) | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_documents_in_dataset**

This will create datasource automatically and create documents in the datasource.
This will only return the newly created datasource and not other datasources from the dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_documents_in_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **create_documents_in_dataset_request** | [**CreateDocumentsInDatasetRequest**](CreateDocumentsInDatasetRequest.md) | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_documents_in_datasource**

Create documents in the datasource of the dataset. This expects datasource to exist.
This will only return the newly added documents in the datasource from the dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_documents_in_datasource).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **datasource_id** | **str** | 
 **create_documents_in_datasource_request** | [**CreateDocumentsInDatasourceRequest**](CreateDocumentsInDatasourceRequest.md) | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_file_datasource**

Creates a datasource in the dataset. Extracts the documents from the file contents and adds them to the datasource.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_file_datasource).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **file** | **bytearray** | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: multipart/form-data
 - **Accept**: */*

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Created |  -  |
**400** | Bad Request |  -  |
**401** | Unauthorized |  -  |
**403** | Forbidden |  -  |
**404** | Not Found |  -  |
**500** | Internal Server Error |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_dataset**

Delete existing dataset and all the datasources linked to it.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#delete_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **delete_datasource**

Delete existing datasource from the dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#delete_datasource).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **datasource_id** | **str** | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **delete_documents_by_document_ids**

Delete documents in the datasource of the dataset. This will not delete the datasource if all the
documents are deleted from it.



### Parameters
Input examples could be found [here](DatasetApiExamples.md#delete_documents_by_document_ids).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **datasource_id** | **str** | 
 **document_ids** | [**List[str]**](str.md) | 

### Return type

void (empty response body)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **get_dataset**

Get dataset based on the provided dataset ID.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **get_datasets**

Get all datasets that you are authorized for.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_datasets).

This endpoint does not need any parameter.

### Return type

[**GetDatasetsResponse**](GetDatasetsResponse.md)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **get_documents**

Get documents in the datasource of the dataset. Specify document-ids to get specific documents.
This will only include the datasource & documents requested and will omit other datasources & documents from the response.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_documents).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **datasource_id** | **str** | 
 **document_ids** | [**List[str]**](str.md) | [optional] 

### Return type

[**ProteanDataset**](ProteanDataset.md)

### HTTP request headers

 - **Content-Type**: Not defined
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

# **search**

Search for documents in specific datasets that closely match provided query. This operation can
utilize full text search, similarity search, reranking to retrieve the best possible match.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#search).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_search_request** | [**DatasetSearchRequest**](DatasetSearchRequest.md) | 

### Return type

[**DatasetSearchResponse**](DatasetSearchResponse.md)

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

# **update_dataset**

Update name of the existing dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#update_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **update_dataset_request** | [**UpdateDatasetRequest**](UpdateDatasetRequest.md) | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

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

# **update_documents**

Update documents in the datasource of the dataset.  The text and metadata fields will be overwritten and not merged.
This will only return the updated documents not all the documents in the datasource.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#update_documents).


Name | Type | Notes
------------- | ------------- | -------------
 **id** | **str** | 
 **datasource_id** | **str** | 
 **update_documents_request** | [**UpdateDocumentsRequest**](UpdateDocumentsRequest.md) | 

### Return type

[**ProteanDataset**](ProteanDataset.md)

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

