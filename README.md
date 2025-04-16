# Protean
The CoGrow Protean Python library provides convenient access to the Protean REST API from any Python 3.11+ application.
The library includes type definitions for all request params and response fields.

## Documentation for API Endpoints

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ChatApi* | [**question**](docs/ChatApi.md#question) | **POST** /api/chat-service/question | RAG enabled text completion.
*DatasetApi* | [**add_file_datasource**](docs/DatasetApi.md#add_file_datasource) | **POST** /api/dataset-service/datasets/{id}/datasources | Add file datasource to the dataset.
*DatasetApi* | [**create_dataset**](docs/DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
*DatasetApi* | [**delete_dataset**](docs/DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{id} | Delete dataset.
*DatasetApi* | [**delete_datasource**](docs/DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{id}/datasources/{datasourceId} | Delete datasource in the dataset.
*DatasetApi* | [**get_dataset**](docs/DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{id} | Get datasource.
*DatasetApi* | [**get_datasets**](docs/DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get datasources.
*DatasetApi* | [**update_dataset**](docs/DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{id} | Update dataset.
*VectorApi* | [**search**](docs/VectorApi.md#search) | **POST** /api/vector-service/vectors/search | Search in vector store


## Documentation For Models

 - [ChatQuestionRequest](docs/ChatQuestionRequest.md)
 - [ChatQuestionResponse](docs/ChatQuestionResponse.md)
 - [ClientToolCall](docs/ClientToolCall.md)
 - [ClientToolDefinition](docs/ClientToolDefinition.md)
 - [ClientTools](docs/ClientTools.md)
 - [CreateDatasetRequest](docs/CreateDatasetRequest.md)
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
 - [ProteanVectorDocument](docs/ProteanVectorDocument.md)
 - [Question500Response](docs/Question500Response.md)
 - [UpdateDatasetRequest](docs/UpdateDatasetRequest.md)
 - [ValidationFailed](docs/ValidationFailed.md)
 - [VectorSearchRequest](docs/VectorSearchRequest.md)
 - [VectorSearchResponse](docs/VectorSearchResponse.md)


## Author

support@cogrow.tech


