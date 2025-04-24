# create_dataset
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateDatasetRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    create_dataset_request = CreateDatasetRequest(name="Test Dataset")
    try:
        create_dataset_response = client.dataset.create_dataset(create_dataset_request=create_dataset_request)
        print("The response of DatasetApi->create_dataset:\n")
        pprint(f"created {create_dataset_response.id}")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_dataset: %s\n" % e)
```
# update_dataset
```python
import os
from pprint import pprint
from protean import Protean, ApiException, UpdateDatasetRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    update_dataset_request = UpdateDatasetRequest(name="Test Dataset")
    try:
        create_dataset_response = client.dataset.update_dataset(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad", 
                                                                update_dataset_request=update_dataset_request)
        print("The response of DatasetApi->update_dataset:\n")
        pprint(f"updated {create_dataset_response.id}")
    except ApiException as e:
        print("Exception when calling DatasetApi->update_dataset: %s\n" % e)
```
# get_dataset
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        get_dataset_response = client.dataset.get_dataset(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad")
        print("The response of DatasetApi->get_dataset:\n")
        pprint(f"created {get_dataset_response.id}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_dataset: %s\n" % e)
```
# get_datasets
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        get_datasets_response = client.dataset.get_datasets()
        print("The response of DatasetApi->get_datasets:\n")
        for dataset in get_datasets_response.datasets:
            pprint(f"retrieved {dataset.id}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_datasets: %s\n" % e)
```
# delete_dataset
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_dataset(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad")
        print("Executed DatasetApi->delete_dataset.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_dataset: %s\n" % e)
```
# create_file_datasource
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset 
        open("./test-file-name.txt", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.create_file_datasource(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad", file=file)
        print("Executed DatasetApi->create_file_datasource.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_file_datasource: %s\n" % e)
```
# delete_datasource
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_datasource(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad", datasource_id="cb0230a0-d0f8-40bf-a0b7-8e7b1b1bb22c")
        print("Executed DatasetApi->delete_datasource.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_datasource: %s\n" % e)
```
# create_documents_in_dataset
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateDocumentsInDatasetRequest, ProteanDocument

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        metadata = {"fileName": "securityPolicy.pdf", "policyVersion": "v1"}
        document1 = ProteanDocument(
            text="All users must authenticate using approved credentials and report suspicious activity immediately to maintain system integrity and data confidentiality.",
            metadata=metadata)
        document2 = ProteanDocument(
            text="Access to confidential data is restricted to authorized personnel only; violations will result in disciplinary action and possible legal consequences.",
            metadata=metadata)
        create_documents_in_dataset_request = CreateDocumentsInDatasetRequest(
            documents=[document1, document2],
            modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
            datasourceName="security-policy",
            embedMetadata=True
        )
        create_documents_in_dataset_response = client.dataset.create_documents_in_dataset(
            id="96a086c8-7417-462b-9d43-1059fdfa6155",
            create_documents_in_dataset_request=create_documents_in_dataset_request)
        print("The response of DatasetApi->create_documents_in_dataset:\n")
        pprint(create_documents_in_dataset_response)

    except ApiException as e:
        print("Exception when calling DatasetApi->create_documents_in_dataset: %s\n" % e)
```
# create_documents_in_datasource
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateDocumentsInDatasourceRequest, ProteanDocument

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        metadata = {"fileName": "securityPolicy.pdf", "policyVersion": "v1"}
        document1 = ProteanDocument(
            text="Passwords must be at least 12 characters long, include symbols, and be changed every 90 days to ensure account security.",
            metadata=metadata)
        document2 = ProteanDocument(
            text="Devices must have up-to-date antivirus software and be encrypted before connecting to the corporate network.",
            metadata=metadata)
        create_documents_in_datasource_request = CreateDocumentsInDatasourceRequest(
            documents=[document1, document2],
            modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
            embedMetadata=True
        )
        create_documents_in_datasource_response = client.dataset.create_documents_in_datasource(
            id="96a086c8-7417-462b-9d43-1059fdfa6155",
            datasource_id="c39703b5-cbad-4234-85ed-e83ab21be072",
            create_documents_in_datasource_request=create_documents_in_datasource_request)
        print("The response of DatasetApi->create_documents_in_datasource:\n")
        pprint(create_documents_in_datasource_response)

    except ApiException as e:
        print("Exception when calling DatasetApi->create_documents_in_datasource: %s\n" % e)
```
# update_documents
```python
import os
from pprint import pprint
from protean import Protean, ApiException, ProteanDocument, UpdateDocumentsRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        metadata = {"fileName": "securityPolicy.pdf", "policyVersion": "v1"}
        document1 = ProteanDocument(
            id="2e651f96-9301-436b-97c8-7749cf2424ed",
            text="All users MUST authenticate using approved credentials and report suspicious activity immediately to maintain system integrity and data confidentiality.",
            metadata=metadata)
        document2 = ProteanDocument(
            id="30ed878c-40ab-434f-a598-5f281a14385d",
            text="Access to ANY confidential data is restricted to authorized personnel only; violations will result in disciplinary action and possible legal consequences.",
            metadata=metadata)
        update_documents_request = UpdateDocumentsRequest(
            documents=[document1, document2],
            modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
            embedMetadata=True
        )
        update_documents_response = client.dataset.update_documents(
            id="96a086c8-7417-462b-9d43-1059fdfa6155",
            datasource_id="c39703b5-cbad-4234-85ed-e83ab21be072",
            update_documents_request=update_documents_request)
        print("The response of DatasetApi->update_documents:\n")
        pprint(update_documents_response)

    except ApiException as e:
        print("Exception when calling DatasetApi->update_documents: %s\n" % e)
```
# delete_documents_by_document_ids
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_documents_by_document_ids(
            id="96a086c8-7417-462b-9d43-1059fdfa6155",
            datasource_id="c39703b5-cbad-4234-85ed-e83ab21be072",
            document_ids=["4d4d3770-89fd-4b55-a011-3a85a28de4d9", "3c309496-6496-4e91-80e8-dfcc5eca3c95"])
        print("Executed DatasetApi->delete_documents_by_document_ids.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_documents_by_document_ids: %s\n" % e)
```
# get_documents
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        protean_dataset = client.dataset.get_documents(
            id="96a086c8-7417-462b-9d43-1059fdfa6155",
            datasource_id="c39703b5-cbad-4234-85ed-e83ab21be072",
            document_ids=[] # omit this property or provide and empty array, to get all the document of the specified datasource
        )
        print("Executed DatasetApi->get_documents_by_datasource_id.")
        pprint(protean_dataset)
    except ApiException as e:
        print("Exception when calling DatasetApi->get_documents_by_datasource_id: %s\n" % e)
```
# search
** Base request that includes foundational configuration parameters, which defaults to Hybrid search with Reranker **
```python
import os
from pprint import pprint
from protean import Protean, ApiException, DatasetSearchRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    dataset_search_request = DatasetSearchRequest(
        query="What are the company security policies for handling data?",
        datasetIds=["*"]  # "*" to query across all authorized datasets.
    )
    try:
        dataset_search_response = client.dataset.search(dataset_search_request=dataset_search_request)
        print("The response of DatasetApi->search:\n")
        pprint(dataset_search_response.documents)
    except ApiException as e:
        print("Exception when calling DatasetApi->search: %s\n" % e)
```
**Request that uses only Similarity search instead of default Hybrid search and doesn't use Reranker**
```python
import os
from pprint import pprint
from protean import Protean, ApiException, DatasetSearchRequest, DatasetSearchType

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    dataset_search_request = DatasetSearchRequest(
        query="What are the company security policies for handling data?",
        datasetIds=["7d9f8d12-c71d-4dea-b425-66c168a1ed19"],
        searchType=DatasetSearchType.SIMILARITY,
        useReranker=False
    )
    try:
        dataset_search_response = client.dataset.search(dataset_search_request=dataset_search_request)
        print("The response of DatasetApi->search:\n")
        pprint(dataset_search_response.documents)
    except ApiException as e:
        print("Exception when calling DatasetApi->search: %s\n" % e)
```
**Request that searches against all documents that include specific Metadata tags**
```python
import os
from pprint import pprint
from protean import Protean, ApiException, DatasetSearchRequest, DatasetSearchType

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    dataset_search_request = DatasetSearchRequest(
        query="What are the company security policies for handling data?",
        datasetIds=["7d9f8d12-c71d-4dea-b425-66c168a1ed19"],
        filterExpression="fileName == 'CorporateSecurityPolicy.pdf' AND datasourceChunk IN [0,1,2]"
    )
    try:
        dataset_search_response = client.dataset.search(dataset_search_request=dataset_search_request)
        print("The response of DatasetApi->search:\n")
        pprint(dataset_search_response.documents)
    except ApiException as e:
        print("Exception when calling DatasetApi->search: %s\n" % e)
```