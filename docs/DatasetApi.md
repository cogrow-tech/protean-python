# DatasetApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_dataset**](DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
[**create_datasource_from_chunks**](DatasetApi.md#create_datasource_from_chunks) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/chunks | Create datasource from chunks.
[**create_datasource_from_file**](DatasetApi.md#create_datasource_from_file) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/file | Create datasource from contents of a file.
[**create_datasource_from_text**](DatasetApi.md#create_datasource_from_text) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/text | Create datasource from the text content.
[**create_documents**](DatasetApi.md#create_documents) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Create documents in the datasource.
[**delete_dataset**](DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{datasetId} | Delete dataset.
[**delete_datasets_by_metadata**](DatasetApi.md#delete_datasets_by_metadata) | **DELETE** /api/dataset-service/datasets | Delete dataset by key.
[**delete_datasource**](DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId} | Delete datasource from the dataset.
[**delete_documents_by_document_ids**](DatasetApi.md#delete_documents_by_document_ids) | **DELETE** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Delete documents in the datasource of the dataset.
[**get_access**](DatasetApi.md#get_access) | **GET** /api/dataset-service/datasets/{datasetId}/access | Get authorization and permissions.
[**get_access_list**](DatasetApi.md#get_access_list) | **POST** /api/dataset-service/datasets/access-list | Get authorization and permissions for all the resources in the request.
[**get_dataset**](DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{datasetId} | Get dataset.
[**get_datasets**](DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get dataset by metadata.
[**get_documents**](DatasetApi.md#get_documents) | **GET** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Get documents in the datasource of the dataset.
[**search**](DatasetApi.md#search) | **POST** /api/dataset-service/datasets/search | Search in dataset(s).
[**update_authorization**](DatasetApi.md#update_authorization) | **PUT** /api/dataset-service/datasets/{datasetId}/authorization | Update authorization for the resource.
[**update_dataset**](DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{datasetId} | Update dataset.
[**update_documents**](DatasetApi.md#update_documents) | **PUT** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Update documents in the datasource of the dataset.


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

# **create_datasource_from_chunks**

Creates a datasource in the dataset, generates embeddings for each input chunk,
 and stores them as documents in the vector database.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_datasource_from_chunks).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 
 **create_datasource_from_chunks_request** | [**CreateDatasourceFromChunksRequest**](CreateDatasourceFromChunksRequest.md) | 

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

# **create_datasource_from_file**

Creates a datasource in the dataset, extracts content from the file, chunks the extracted content,
generates embeddings for each chunk, and stores them as documents in the vector database.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_datasource_from_file).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 
 **file** | **bytearray** | 
 **datasource_request** | [**CreateDatasourceRequest**](CreateDatasourceRequest.md) | [optional] 

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

# **create_datasource_from_text**

Creates a datasource in the dataset, chunks the input text, generates embeddings for each chunk,
 and stores them as documents in the vector database.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_datasource_from_text).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 
 **create_datasource_request** | [**CreateDatasourceRequest**](CreateDatasourceRequest.md) | 

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

# **create_documents**

Create documents in the datasource of the dataset. This expects datasource to exist.
This will only return the newly added documents in the datasource from the dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#create_documents).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 
 **datasource_id** | **str** | 
 **create_documents_request** | [**CreateDocumentsRequest**](CreateDocumentsRequest.md) | 

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

# **delete_dataset**

Delete existing dataset and all the datasources linked to it.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#delete_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 

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

# **delete_datasets_by_metadata**

Delete existing dataset and all the datasources linked to it.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#delete_datasets_by_metadata).


Name | Type | Notes
------------- | ------------- | -------------
 **key** | **str** | 
 **value** | **str** | 

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
 **dataset_id** | **str** | 
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
 **dataset_id** | **str** | 
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

# **get_access**

This provides details about who has access to the resource (owners, viewers) and the actions (permissions) the authenticated user is allowed to perform on it.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_access).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 

### Return type

[**Access**](Access.md)

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

# **get_access_list**

This provides details about who has access to the resource (owners, viewers) and the actions (permissions) the authenticated user is allowed to perform on it.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_access_list).


Name | Type | Notes
------------- | ------------- | -------------
 **get_access_list_request** | [**GetAccessListRequest**](GetAccessListRequest.md) | 

### Return type

[**GetAccessListResponse**](GetAccessListResponse.md)

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

# **get_dataset**

Get dataset based on the provided dataset ID.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_dataset).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 

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

Get dataset based on the provided key. Omit key to return all authorized datasets.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#get_datasets).


Name | Type | Notes
------------- | ------------- | -------------
 **key** | **str** | [optional] 
 **value** | **str** | [optional] 

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
 **dataset_id** | **str** | 
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

# **update_authorization**

This will replace all existing authorizations for the resource, so be sure to provide the full set of authorizations when updating.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#update_authorization).


Name | Type | Notes
------------- | ------------- | -------------
 **dataset_id** | **str** | 
 **update_authorization_request** | [**UpdateAuthorizationRequest**](UpdateAuthorizationRequest.md) | 

### Return type

[**Authorization**](Authorization.md)

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
 **dataset_id** | **str** | 
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
 **dataset_id** | **str** | 
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

