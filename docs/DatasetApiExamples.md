# create_dataset
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateDatasetRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    metadata = {
        "priority": "HIGH"
    }
    create_dataset_request = CreateDatasetRequest(name="Test Dataset", metadata=metadata)
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
    metadata = {
        "priority": "LOW"
    }
    update_dataset_request = UpdateDatasetRequest(name="Test Dataset - upd", metadata=metadata)
    try:

        update_dataset_response = client.dataset.update_dataset(dataset_id="d26b34e3-c993-43bc-8085-e15c1194c5a4",
                                                                update_dataset_request=update_dataset_request)
        print("The response of DatasetApi->update_dataset:\n")
        pprint(f"updated {update_dataset_response.id}")
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
        get_dataset_response = client.dataset.get_dataset(dataset_id="d26b34e3-c993-43bc-8085-e15c1194c5a4")
        print("The response of DatasetApi->get_dataset:\n")
        pprint(f"dataset {get_dataset_response}")
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
            pprint(f"retrieved {dataset}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_datasets: %s\n" % e)
```
# get_datasets_by_metadata
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        get_datasets_response = client.dataset.get_datasets(key="priority", value="HIGH" )
        print("The response of DatasetApi->get_datasets:\n")
        for dataset in get_datasets_response.datasets:
            pprint(f"retrieved {dataset}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_datasets: %s\n" % e)
```
# delete_dataset
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_dataset(dataset_id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad")
        print("Executed DatasetApi->delete_dataset.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_dataset: %s\n" % e)
```
# delete_datasets_by_metadata
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_datasets_by_metadata(key="priority", value="HIGH")
        print("Executed DatasetApi->delete_datasets_by_metadata:\n.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_datasets_by_metadata: %s\n" % e)
```
# get_access
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        access = client.dataset.get_access(dataset_id="c5e11bb4-512b-4efd-bec1-ac49c86a39c0")
        print("The response of DatasetApi->get_access:\n")
        pprint(f"access {access}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_access: %s\n" % e)
```
# get_access_list
```python
import os
from pprint import pprint
from protean import Protean, ApiException, GetAccessListRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        resource_ids = ["c5e11bb4-512b-4efd-bec1-ac49c86a39c0", "767459e2-e111-4699-bc40-a7ad64295eb4"]
        get_access_list_request = GetAccessListRequest(resourceIds=resource_ids)
        get_access_list_response = client.dataset.get_access_list(get_access_list_request)
        print("The response of DatasetApi->get_access_list:\n")
        pprint(f"get_access_list_response {get_access_list_response}")
    except ApiException as e:
        print("Exception when calling DatasetApi->get_access_list: %s\n" % e)
```
# update_authorization
```python
import os
from pprint import pprint
from protean import Protean, ApiException, UpdateAuthorizationRequest, EmbeddableUser

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        resource_id = "c5e11bb4-512b-4efd-bec1-ac49c86a39c0"
        resource_type = "DATASET"
        owner_user = EmbeddableUser(id="user1@email.com", email="user1@email.com", fullname="user1 lastname1")
        owner_users = [owner_user]
        owner_groups = ["dataset_owner_group"]
        viewer_groups = ["Everyone"]
        viewer_user = EmbeddableUser(id="user2@email.com", email="user2@email.com", fullname="user2 lastname2")
        viewer_users = [viewer_user]
        update_authorization_request = UpdateAuthorizationRequest(resourceId=resource_id,
                                                                  resourceType=resource_type,
                                                                  ownerUsers= owner_users,
                                                                  ownerGroups = owner_groups,
                                                                  viewerUsers = viewer_users,
                                                                  viewerGroups = viewer_groups)
        update_authorization_response = client.dataset.update_authorization(resource_id, update_authorization_request)
        print("The response of DatasetApi->update_authorization:\n")
        pprint(f"update_authorization {update_authorization_response}")
    except ApiException as e:
        print("Exception when calling DatasetApi->update_authorization: %s\n" % e)
```
# create_datasource_from_file
** Request that uses defaults **
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("./README.md", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.create_datasource_from_file(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4", file=file)
        print("Executed DatasetApi->create_datasource_from_file.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_file: %s\n" % e)
```
** Request that uses fixed chunking **
```python
import os
from protean import Protean, ApiException, CreateFixedSizeChunksRequest, CreateDatasourceRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    chunk_size = 20
    min_chunk_size_chars = 15
    min_chunk_length_to_embed = 15
    max_num_chunks = 40
    keep_separator = True
    create_fixed_size_chunks_request = CreateFixedSizeChunksRequest(
        chunkSize=chunk_size, #The target size of each text chunk in tokens.
        minChunkSizeChars=min_chunk_size_chars, #The minimum size of each text chunk in characters.
        minChunkLengthToEmbed=min_chunk_length_to_embed, #The minimum length of a chunk to be included.
        maxNumChunks=max_num_chunks, #The maximum number of chunks to generate from a text.
        keepSeparator=keep_separator #Whether to keep separators (like newlines) in the chunks
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        fixedSizeChunking=create_fixed_size_chunks_request)
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.create_datasource_from_file(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4", file=file, datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_file.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_file: %s\n" % e)
```
** Request that uses semantic chunking **
```python
import os

from protean import Protean, ApiException, CreateDatasourceRequest, TextSplittingStrategy, \
    CombiningStrategy, SimilarityStrategy, BreakpointStrategy, CreateSemanticChunksRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    text_splitting_strategy = TextSplittingStrategy.SENTENCE_DISAMBIGUATION
    combining_strategy = CombiningStrategy.ADJACENT_LINES
    buffer_size = 1
    similarity_strategy = SimilarityStrategy.COSINE
    breakpoint_strategy = BreakpointStrategy.PERCENTILE
    breakpoint_threshold_tuner = 85
    maximum_chunk_size = 800
    generate_embeddings = False
    create_semantic_chunks_request = CreateSemanticChunksRequest(
        textSplittingStrategy=text_splitting_strategy, # SENTENCE_DISAMBIGUATION is default, can also be SENTENCE_DELIMITER
        combiningStrategy=combining_strategy, # ADJACENT_LINES is default, can also be SLIDING_WINDOW or TUMBLING_WINDOW
        bufferSize=buffer_size, # determines the size of window with SLIDING_WINDOW or TUMBLING_WINDOW and number of adjacent lines to combine with ADJACENT_LINES
        similarityStrategy=similarity_strategy,
        breakpointStrategy=breakpoint_strategy, # PERCENTILE is default, can also be STANDARD_DEVIATION, INTERQUARTILE or GRADIENT
        breakpointThresholdTuner=breakpoint_threshold_tuner, #Determines the sensitivity of the breakpoint strategy
        maximumChunkSize=maximum_chunk_size, #After semantic chunking, if the resulting chunk sizes are bigger than this, the chunks will be broken further.
        generateEmbeddings=generate_embeddings #Generate and return embedding together with the chunks
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        sematicChunking=create_semantic_chunks_request)
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.create_datasource_from_file(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4", file=file, datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_file.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_file: %s\n" % e)
```
** Request that uses late chunking **
```python
import os

from protean import Protean, ApiException, CreateDatasourceRequest, TextSplittingStrategy, \
    CreateLateChunksRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    text_splitting_strategy = TextSplittingStrategy.SENTENCE_DISAMBIGUATION
    chunk_size = 800
    overlap_percentage = 10

    create_late_chunks_request = CreateLateChunksRequest(
        #embedding_model=modelId, # Model that is deployed with pooling='none'
        textSplittingStrategy=text_splitting_strategy,
        chunkSize=chunk_size,
        overlapPercentage=overlap_percentage
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        lateChunking=create_late_chunks_request)
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.create_datasource_from_file(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4", file=file, datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_file.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_file: %s\n" % e)
```
# create_datasource_from_text
** Request that uses defaults **
```python
import os
from protean import Protean, ApiException, CreateFixedSizeChunksRequest, CreateDatasourceRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    create_fixed_size_chunks_request = CreateFixedSizeChunksRequest(
        text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe."
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        fixedSizeChunking=create_fixed_size_chunks_request)
    try:
        client.dataset.create_datasource_from_text(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
                                                   create_datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_text.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_text: %s\n" % e)
```
** Request that uses fixed size chunking inputs **
```python
import os
from protean import Protean, ApiException, CreateFixedSizeChunksRequest, CreateDatasourceRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    chunk_size = 20
    min_chunk_size_chars = 15
    min_chunk_length_to_embed = 15
    max_num_chunks = 40
    keep_separator = True
    create_fixed_size_chunks_request = CreateFixedSizeChunksRequest(
        text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe.",
        chunkSize=chunk_size, #The target size of each text chunk in tokens.
        minChunkSizeChars=min_chunk_size_chars, #The minimum size of each text chunk in characters.
        minChunkLengthToEmbed=min_chunk_length_to_embed, #The minimum length of a chunk to be included.
        maxNumChunks=max_num_chunks, #The maximum number of chunks to generate from a text.
        keepSeparator=keep_separator #Whether to keep separators (like newlines) in the chunks
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        fixedSizeChunking=create_fixed_size_chunks_request)
    try:
        client.dataset.create_datasource_from_text(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
                                                   create_datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_text.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_text: %s\n" % e)
```
** Request that uses semantic chunking inputs **
```python
import os
from protean import Protean, ApiException, CreateSemanticChunksRequest, CreateDatasourceRequest, \
    TextSplittingStrategy, BreakpointStrategy, SimilarityStrategy, CombiningStrategy

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    text_splitting_strategy = TextSplittingStrategy.SENTENCE_DISAMBIGUATION
    combining_strategy = CombiningStrategy.ADJACENT_LINES
    buffer_size = 1
    similarity_strategy = SimilarityStrategy.COSINE
    breakpoint_strategy = BreakpointStrategy.PERCENTILE
    breakpoint_threshold_tuner = 85
    maximum_chunk_size = 800
    generate_embeddings = False

    create_semantic_chunks_request = CreateSemanticChunksRequest(
        text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe.",
        textSplittingStrategy=text_splitting_strategy, # SENTENCE_DISAMBIGUATION is default, can also be SENTENCE_DELIMITER
        combiningStrategy=combining_strategy, # ADJACENT_LINES is default, can also be SLIDING_WINDOW or TUMBLING_WINDOW
        bufferSize=buffer_size, # determines the size of window with SLIDING_WINDOW or TUMBLING_WINDOW and number of adjacent lines to combine with ADJACENT_LINES
        similarityStrategy=similarity_strategy,
        breakpointStrategy=breakpoint_strategy, # PERCENTILE is default, can also be STANDARD_DEVIATION, INTERQUARTILE or GRADIENT
        breakpointThresholdTuner=breakpoint_threshold_tuner, #Determines the sensitivity of the breakpoint strategy
        maximumChunkSize=maximum_chunk_size, #After semantic chunking, if the resulting chunk sizes are bigger than this, the chunks will be broken further.
        generateEmbeddings=generate_embeddings #Generate and return embedding together with the chunks
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        sematicChunking=create_semantic_chunks_request)
    try:
        client.dataset.create_datasource_from_text(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
                                                   create_datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_text.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_text: %s\n" % e)
```
** Request that uses late chunking inputs **
```python
import os
from protean import Protean, ApiException, CreateLateChunksRequest, CreateDatasourceRequest, TextSplittingStrategy

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    text_splitting_strategy = TextSplittingStrategy.SENTENCE_DISAMBIGUATION
    chunk_size = 800
    overlap_percentage = 10

    create_late_chunks_request = CreateLateChunksRequest(
        text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe.",
        #embedding_model=modelId, # Model that is deployed with pooling='none'
        textSplittingStrategy=text_splitting_strategy,
        chunkSize=chunk_size,
        overlapPercentage=overlap_percentage
    )
    create_datasource_request = CreateDatasourceRequest(
        datasourceName="my-datasource",
        lateChunking=create_late_chunks_request)
    try:
        client.dataset.create_datasource_from_text(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
                                                   create_datasource_request=create_datasource_request)
        print("Executed DatasetApi->create_datasource_from_text.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_text: %s\n" % e)
```
# create_datasource_from_chunks
```python
import os
from protean import Protean, ApiException, CreateDatasourceFromChunksRequest, ProteanDocument

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    metadata = {"fileName": "securityPolicy.pdf", "policyVersion": "v1"}
    document1 = ProteanDocument(
        text="All users must authenticate using approved credentials and report suspicious activity immediately to maintain system integrity and data confidentiality.",
        metadata=metadata)
    document2 = ProteanDocument(
        text="Access to confidential data is restricted to authorized personnel only; violations will result in disciplinary action and possible legal consequences.",
        metadata=metadata)
    create_datasource_from_chunks_request = CreateDatasourceFromChunksRequest(
        documents=[document1, document2],
        datasourceName="security-policy"
        #modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
    )
    try:
        client.dataset.create_datasource_from_chunks(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4", create_datasource_from_chunks_request=create_datasource_from_chunks_request)
        print("Executed DatasetApi->create_datasource_from_text.")
    except ApiException as e:
        print("Exception when calling DatasetApi->create_datasource_from_chunks: %s\n" % e)
```
# delete_datasource
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        client.dataset.delete_datasource(dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
                                         datasource_id="cf99ffac-9c50-465b-95a4-3ad8b690b698")
        print("Executed DatasetApi->delete_datasource.")
    except ApiException as e:
        print("Exception when calling DatasetApi->delete_datasource: %s\n" % e)
```
# create_documents
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateDocumentsRequest, ProteanDocument

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    try:
        metadata = {"fileName": "securityPolicy.pdf", "policyVersion": "v1"}
        document1 = ProteanDocument(
            text="Passwords must be at least 12 characters long, include symbols, and be changed every 90 days to ensure account security.",
            metadata=metadata)
        document2 = ProteanDocument(
            text="Devices must have up-to-date antivirus software and be encrypted before connecting to the corporate network.",
            metadata=metadata)
        create_documents_request = CreateDocumentsRequest(
            documents=[document1, document2],
            modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
            embedMetadata=True
        )
        create_documents_response = client.dataset.create_documents(
            dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
            datasource_id="b0b43674-fa14-401a-aeda-441af3392c4c",
            create_documents_request=create_documents_request)
        print("The response of DatasetApi->create_documents:\n")
        pprint(create_documents_response)

    except ApiException as e:
        print("Exception when calling DatasetApi->create_documents: %s\n" % e)
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
            id="0d34055f-e818-41fd-96ef-a6d004dc463e",
            text="All users MUST authenticate using approved credentials and report suspicious activity immediately to maintain system integrity and data confidentiality.",
            metadata=metadata)
        document2 = ProteanDocument(
            id="70e5a3cb-20e0-4cc9-9006-924a608fe8b7",
            text="Access to ANY confidential data is restricted to authorized personnel only; violations will result in disciplinary action and possible legal consequences.",
            metadata=metadata)
        update_documents_request = UpdateDocumentsRequest(
            documents=[document1, document2],
            modelId="bge-m3",  # omit modelId to use default model for embeddings generation.
            embedMetadata=True
        )
        update_documents_response = client.dataset.update_documents(
            dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
            datasource_id="b0b43674-fa14-401a-aeda-441af3392c4c",
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
            dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
            datasource_id="b0b43674-fa14-401a-aeda-441af3392c4c",
            document_ids=["0d34055f-e818-41fd-96ef-a6d004dc463e", "70e5a3cb-20e0-4cc9-9006-924a608fe8b7"])
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
            dataset_id="767459e2-e111-4699-bc40-a7ad64295eb4",
            datasource_id="787d86a6-8766-43e7-a264-673e77e2278e",
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
**Request that searches against all documents that include specific Metadata**
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