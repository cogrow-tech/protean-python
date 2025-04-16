# DatasetApi

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_file_datasource**](DatasetApi.md#add_file_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources | Add file datasource to the dataset.
[**create_dataset**](DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
[**delete_dataset**](DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{id} | Delete dataset.
[**delete_datasource**](DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId} | Delete datasource in the dataset.
[**get_dataset**](DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{id} | Get datasource.
[**get_datasets**](DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get datasources.
[**update_dataset**](DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{id} | Update dataset.


# **add_file_datasource**

Add file content as a datasource to existing dataset.


### Parameters
Input examples could be found [here](DatasetApiExamples.md#add_file_datasource).


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

Delete existing datasource in the existing dataset.


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

# **get_dataset**

Get datasource based on the provided datasource ID.


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

Get all datasources that you are authorized for.


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

