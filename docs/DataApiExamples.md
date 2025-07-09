# convert_file_to_markdown
```python
import os
from pprint import pprint
from protean import Protean, ApiException, ConvertFileToMdRequest, TableProcessingMode

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    convert_file_to_md_request = ConvertFileToMdRequest(
        includeImages=False,
        tableProcessingMode=TableProcessingMode.FAST
    )
    file = (
        "test.pdf",  # Name of the file to be converted, file extension must be one of the following: pdf, docx, pptx, xlsx, html, csv
        open("./test.pdf", "rb").read()  # File content in either binary or string format
    )

    try:
        convert_file_to_md_response = client.data.convert_file_to_md(
            file=file,
            convert_file_to_md_request=convert_file_to_md_request)
        print("The response of DataApi->convert_file_to_md_response:\n")
        pprint(f"created {convert_file_to_md_response}")
    except ApiException as e:
        print("Exception when calling DataApi->convert_file_to_md: %s\n" % e)
```
# create_fixed_size_chunks_from_file
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateFixedSizeChunksRequest

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
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )

    try:
        create_fixed_size_chunks_response = client.data.create_fixed_size_chunks_from_file(
            file=file,
            create_fixed_size_chunks_request=create_fixed_size_chunks_request)
        print("The response of DataApi->create_fixed_size_chunks_response:\n")
        pprint(f"created {create_fixed_size_chunks_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_fixed_size_chunks_from_file: %s\n" % e)
```
# create_fixed_size_chunks_from_text
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateFixedSizeChunksRequest

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

    try:
        create_fixed_size_chunks_response = client.data.create_fixed_size_chunks_from_text(
            create_fixed_size_chunks_request=create_fixed_size_chunks_request)
        print("The response of DataApi->create_fixed_size_chunks_response:\n")
        pprint(f"created {create_fixed_size_chunks_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_fixed_size_chunks_response: %s\n" % e)
```
# create_semantic_chunks_from_file
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateSemanticChunksRequest, TextSplittingStrategy, CombiningStrategy, SimilarityStrategy, BreakpointStrategy

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
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )

    try:
        create_semantic_chunk_response = client.data.create_semantic_chunks_from_file(
            file=file,
            create_semantic_chunks_request=create_semantic_chunks_request)
        print("The response of DataApi->create_semantic_chunk:\n")
        pprint(f"created {create_semantic_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_semantic_chunks_from_file: %s\n" % e)
```
# create_semantic_chunks_from_text
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateSemanticChunksRequest, TextSplittingStrategy, CombiningStrategy, SimilarityStrategy, BreakpointStrategy

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

    try:
        create_semantic_chunk_response = client.data.create_semantic_chunks_from_text(
            create_semantic_chunks_request=create_semantic_chunks_request)
        print("The response of DataApi->create_semantic_chunks_from_text:\n")
        pprint(f"created {create_semantic_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_semantic_chunks_from_text: %s\n" % e)
```
# create_late_chunks_from_file

```python
import os
from pprint import pprint
from protean import Protean, ApiException, TextSplittingStrategy, CreateLateChunksRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    text_splitting_strategy = TextSplittingStrategy.SENTENCE_DISAMBIGUATION
    chunk_size = 800
    overlap_percentage = 10
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset
        open("/Users/harshitkapoor/Documents/Projects/cogrow/protean/protean-sdk-python/test.txt", "rb").read() # File content in either binary or string format
    )
    create_late_chunks_request = CreateLateChunksRequest(
        embeddingModel="late-chunk-embedding", # Model that is deployed with pooling='none'
        textSplittingStrategy=text_splitting_strategy,
        chunkSize=chunk_size,
        overlapPercentage=overlap_percentage
    )

    try:
        create_late_chunk_response = client.data.create_late_chunks_from_file(
            file=file,
            create_late_chunks_request=create_late_chunks_request)
        print("The response of DataApi->create_late_chunks_from_file:\n")
        pprint(f"created {create_late_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_late_chunks_from_file: %s\n" % e)
```
# create_late_chunks_from_text

```python
import os
from pprint import pprint
from protean import Protean, ApiException, TextSplittingStrategy, CreateLateChunksRequest

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

    try:
        create_late_chunk_response = client.data.create_late_chunks_from_text(
            create_late_chunks_request=create_late_chunks_request)
        print("The response of DataApi->create_late_chunks_from_text:\n")
        pprint(f"created {create_late_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_late_chunks_from_text: %s\n" % e)
```

