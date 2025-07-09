# Protean
The CoGrow Protean Python library provides convenient access to the Protean REST API from any Python 3.11+ application.
The library includes type definitions for all request params and response fields.

## Documentation for API Endpoints

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ChatApi* | [**question**](docs/ChatApi.md#question) | **POST** /api/chat-service/question | RAG enabled text completion.
*DataApi* | [**convert_file_to_markdown**](docs/DataApi.md#convert_file_to_markdown) | **POST** /api/data-service/data/extract/file/convert-to-md | Convert file content into markdown.
*DataApi* | [**create_embeddings**](docs/DataApi.md#create_embeddings) | **POST** /api/data-service/data/embed | Creates embeddings for texts.
*DataApi* | [**create_fixed_size_chunks_from_file**](docs/DataApi.md#create_fixed_size_chunks_from_file) | **POST** /api/data-service/data/chunk/file/fixed-size | Splits file contents into chunks based on token count.
*DataApi* | [**create_fixed_size_chunks_from_text**](docs/DataApi.md#create_fixed_size_chunks_from_text) | **POST** /api/data-service/data/chunk/text/fixed-size | Splits text into chunks based on token count.
*DataApi* | [**create_late_chunks_from_file**](docs/DataApi.md#create_late_chunks_from_file) | **POST** /api/data-service/data/chunk/file/late | Splits contents of file into chunks using late chunking technique. The model being used to perform chunking must have pooling&#x3D;&#39;none&#39;
*DataApi* | [**create_late_chunks_from_text**](docs/DataApi.md#create_late_chunks_from_text) | **POST** /api/data-service/data/chunk/text/late |
*DataApi* | [**create_semantic_chunks_from_file**](docs/DataApi.md#create_semantic_chunks_from_file) | **POST** /api/data-service/data/chunk/file/semantic | Splits contents of file into chunks that are semantically similar.
*DataApi* | [**create_semantic_chunks_from_text**](docs/DataApi.md#create_semantic_chunks_from_text) | **POST** /api/data-service/data/chunk/text/semantic | Splits text into chunks that are semantically similar.
*DatasetApi* | [**create_dataset**](docs/DatasetApi.md#create_dataset) | **POST** /api/dataset-service/datasets | Create dataset.
*DatasetApi* | [**create_datasource_from_chunks**](docs/DatasetApi.md#create_datasource_from_chunks) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/chunks | Create datasource from chunks.
*DatasetApi* | [**create_datasource_from_file**](docs/DatasetApi.md#create_datasource_from_file) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/file | Create datasource from contents of a file.
*DatasetApi* | [**create_datasource_from_text**](docs/DatasetApi.md#create_datasource_from_text) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/text | Create datasource from the text content.
*DatasetApi* | [**create_documents**](docs/DatasetApi.md#create_documents) | **POST** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Create documents in the datasource.
*DatasetApi* | [**delete_dataset**](docs/DatasetApi.md#delete_dataset) | **DELETE** /api/dataset-service/datasets/{datasetId} | Delete dataset.
*DatasetApi* | [**delete_datasets_by_metadata**](docs/DatasetApi.md#delete_datasets_by_metadata) | **DELETE** /api/dataset-service/datasets | Delete dataset by key.
*DatasetApi* | [**delete_datasource**](docs/DatasetApi.md#delete_datasource) | **DELETE** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId} | Delete datasource from the dataset.
*DatasetApi* | [**delete_documents_by_document_ids**](docs/DatasetApi.md#delete_documents_by_document_ids) | **DELETE** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Delete documents in the datasource of the dataset.
*DatasetApi* | [**get_access**](docs/DatasetApi.md#get_access) | **GET** /api/dataset-service/datasets/{datasetId}/access | Get authorization and permissions.
*DatasetApi* | [**get_access_list**](docs/DatasetApi.md#get_access_list) | **POST** /api/dataset-service/datasets/access-list | Get authorization and permissions for all the resources in the request.
*DatasetApi* | [**get_dataset**](docs/DatasetApi.md#get_dataset) | **GET** /api/dataset-service/datasets/{datasetId} | Get dataset.
*DatasetApi* | [**get_datasets**](docs/DatasetApi.md#get_datasets) | **GET** /api/dataset-service/datasets | Get dataset by metadata.
*DatasetApi* | [**get_documents**](docs/DatasetApi.md#get_documents) | **GET** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Get documents in the datasource of the dataset.
*DatasetApi* | [**search**](docs/DatasetApi.md#search) | **POST** /api/dataset-service/datasets/search | Search in dataset(s).
*DatasetApi* | [**update_authorization**](docs/DatasetApi.md#update_authorization) | **PUT** /api/dataset-service/datasets/{datasetId}/authorization | Update authorization for the resource.
*DatasetApi* | [**update_dataset**](docs/DatasetApi.md#update_dataset) | **PUT** /api/dataset-service/datasets/{datasetId} | Update dataset.
*DatasetApi* | [**update_documents**](docs/DatasetApi.md#update_documents) | **PUT** /api/dataset-service/datasets/{datasetId}/datasources/{datasourceId}/documents | Update documents in the datasource of the dataset.
*UserApi* | [**get_user_profile**](docs/UserApi.md#get_user_profile) | **GET** /api/auth-service/users/me/profile | Get authenticated user&#39;s profile.


## Documentation For Models

- [Access](docs/Access.md)
- [Authorization](docs/Authorization.md)
- [BreakpointStrategy](docs/BreakpointStrategy.md)
- [ChatQuestionRequest](docs/ChatQuestionRequest.md)
- [ChatQuestionResponse](docs/ChatQuestionResponse.md)
- [Chunk](docs/Chunk.md)
- [ClientToolCall](docs/ClientToolCall.md)
- [ClientToolDefinition](docs/ClientToolDefinition.md)
- [ClientTools](docs/ClientTools.md)
- [CombiningStrategy](docs/CombiningStrategy.md)
- [ConvertFileToMarkdownRequest](docs/ConvertFileToMarkdownRequest.md)
- [ConvertFileToMdRequest](docs/ConvertFileToMdRequest.md)
- [ConvertFileToMdResponse](docs/ConvertFileToMdResponse.md)
- [CreateDatasetRequest](docs/CreateDatasetRequest.md)
- [CreateDatasourceFromChunksRequest](docs/CreateDatasourceFromChunksRequest.md)
- [CreateDatasourceFromFileRequest](docs/CreateDatasourceFromFileRequest.md)
- [CreateDatasourceRequest](docs/CreateDatasourceRequest.md)
- [CreateDocumentsRequest](docs/CreateDocumentsRequest.md)
- [CreateEmbeddingsRequest](docs/CreateEmbeddingsRequest.md)
- [CreateEmbeddingsResponse](docs/CreateEmbeddingsResponse.md)
- [CreateFixedSizeChunksFromFileRequest](docs/CreateFixedSizeChunksFromFileRequest.md)
- [CreateFixedSizeChunksRequest](docs/CreateFixedSizeChunksRequest.md)
- [CreateFixedSizeChunksResponse](docs/CreateFixedSizeChunksResponse.md)
- [CreateLateChunksFromFileRequest](docs/CreateLateChunksFromFileRequest.md)
- [CreateLateChunksRequest](docs/CreateLateChunksRequest.md)
- [CreateLateChunksResponse](docs/CreateLateChunksResponse.md)
- [CreateSemanticChunksFromFileRequest](docs/CreateSemanticChunksFromFileRequest.md)
- [CreateSemanticChunksRequest](docs/CreateSemanticChunksRequest.md)
- [CreateSemanticChunksResponse](docs/CreateSemanticChunksResponse.md)
- [DatasetSearchRequest](docs/DatasetSearchRequest.md)
- [DatasetSearchResponse](docs/DatasetSearchResponse.md)
- [DatasetSearchType](docs/DatasetSearchType.md)
- [EmbeddableUser](docs/EmbeddableUser.md)
- [ExceptionResponse](docs/ExceptionResponse.md)
- [GetAccessListRequest](docs/GetAccessListRequest.md)
- [GetAccessListResponse](docs/GetAccessListResponse.md)
- [GetDatasetsResponse](docs/GetDatasetsResponse.md)
- [InternalError](docs/InternalError.md)
- [InternalErrorCause](docs/InternalErrorCause.md)
- [InternalErrorCauseStackTraceInner](docs/InternalErrorCauseStackTraceInner.md)
- [NotAuthenticated](docs/NotAuthenticated.md)
- [NotAuthorized](docs/NotAuthorized.md)
- [NotFound](docs/NotFound.md)
- [Permission](docs/Permission.md)
- [ProteanDataset](docs/ProteanDataset.md)
- [ProteanDatasource](docs/ProteanDatasource.md)
- [ProteanDocument](docs/ProteanDocument.md)
- [Question500Response](docs/Question500Response.md)
- [Sentence](docs/Sentence.md)
- [SimilarityStrategy](docs/SimilarityStrategy.md)
- [TableProcessingMode](docs/TableProcessingMode.md)
- [TextSplittingStrategy](docs/TextSplittingStrategy.md)
- [UpdateAuthorizationRequest](docs/UpdateAuthorizationRequest.md)
- [UpdateDatasetRequest](docs/UpdateDatasetRequest.md)
- [UpdateDocumentsRequest](docs/UpdateDocumentsRequest.md)
- [User](docs/User.md)
- [ValidationFailed](docs/ValidationFailed.md)


## Author

support@cogrow.tech


