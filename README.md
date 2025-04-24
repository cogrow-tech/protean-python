# Protean
The CoGrow Protean Python library provides convenient access to the Protean REST API from any Python 3.11+ application.
The library includes type definitions for all request params and response fields.

## Documentation for API Endpoints

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ChatApi* | [**question**](docs/ChatApi.md#question) | **POST** /api/chat-service/question | RAG enabled text completion.
*DatasetApi* | [**create_dataset**](docs/DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
*DatasetApi* | [**create_documents_in_dataset**](docs/DatasetApi.md#create_documents_in_dataset) | **POST** /api/dataset-service/datasets/{id}/datasources/documents | Create documents in the dataset.
*DatasetApi* | [**create_documents_in_datasource**](docs/DatasetApi.md#create_documents_in_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Create documents in the datasource.
*DatasetApi* | [**create_file_datasource**](docs/DatasetApi.md#create_file_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources/file | Create file datasource in the dataset.
*DatasetApi* | [**delete_dataset**](docs/DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{id} | Delete dataset.
*DatasetApi* | [**delete_datasource**](docs/DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId} | Delete datasource from the dataset.
*DatasetApi* | [**delete_documents_by_document_ids**](docs/DatasetApi.md#delete_documents_by_document_ids) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Delete documents in the datasource of the dataset.
*DatasetApi* | [**get_dataset**](docs/DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{id} | Get dataset.
*DatasetApi* | [**get_datasets**](docs/DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get datasets.
*DatasetApi* | [**get_documents**](docs/DatasetApi.md#get_documents) | **GET** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Get documents in the datasource of the dataset.
*DatasetApi* | [**search**](docs/DatasetApi.md#search) | **POST** /api/dataset-service/datasets/search | Search in dataset(s).
*DatasetApi* | [**update_dataset**](docs/DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{id} | Update dataset.
*DatasetApi* | [**update_documents**](docs/DatasetApi.md#update_documents) | **PUT** /api/dataset-service/datasets/{id}/datasources/{datasourceId}/documents | Update documents in the datasource of the dataset.


## Documentation For Models

 - [ChatQuestionRequest](docs/ChatQuestionRequest.md)
 - [ChatQuestionResponse](docs/ChatQuestionResponse.md)
 - [ClientToolCall](docs/ClientToolCall.md)
 - [ClientToolDefinition](docs/ClientToolDefinition.md)
 - [ClientTools](docs/ClientTools.md)
 - [CreateDatasetRequest](docs/CreateDatasetRequest.md)
 - [CreateDocumentsInDatasetRequest](docs/CreateDocumentsInDatasetRequest.md)
 - [CreateDocumentsInDatasourceRequest](docs/CreateDocumentsInDatasourceRequest.md)
 - [DatasetSearchRequest](docs/DatasetSearchRequest.md)
 - [DatasetSearchResponse](docs/DatasetSearchResponse.md)
 - [DatasetSearchType](docs/DatasetSearchType.md)
 - [ExceptionResponse](docs/ExceptionResponse.md)
 - [GetDatasetsResponse](docs/GetDatasetsResponse.md)
 - [InternalError](docs/InternalError.md)
 - [NotAuthenticated](docs/NotAuthenticated.md)
 - [NotAuthorized](docs/NotAuthorized.md)
 - [NotFound](docs/NotFound.md)
 - [NotFoundCause](docs/NotFoundCause.md)
 - [NotFoundCauseStackTraceInner](docs/NotFoundCauseStackTraceInner.md)
 - [ProteanDataset](docs/ProteanDataset.md)
 - [ProteanDatasource](docs/ProteanDatasource.md)
 - [ProteanDocument](docs/ProteanDocument.md)
 - [Question500Response](docs/Question500Response.md)
 - [UpdateDatasetRequest](docs/UpdateDatasetRequest.md)
 - [UpdateDocumentsRequest](docs/UpdateDocumentsRequest.md)
 - [ValidationFailed](docs/ValidationFailed.md)


## Author

support@cogrow.tech


