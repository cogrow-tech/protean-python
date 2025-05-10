from test import create_fixed_size_chunks_requestfrom build.lib.protean.models.text_splitting_strategy import TextSplittingStrategyfrom build.lib.protean.models.create_semantic_chunks_request import CreateSemanticChunksRequest

# create_semantic_chunks
** Base request that uses defaults **
```python
import os
from pprint import pprint
from protean import Protean, ApiException, CreateSemanticChunksRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    create_semantic_chunks_request = CreateSemanticChunksRequest(text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe.")
    try:
        create_semantic_chunk_response = client.data.create_semantic_chunks(create_semantic_chunks_request = create_semantic_chunks_request)
        print("The response of DataApi->create_semantic_chunk:\n")
        pprint(f"created {create_semantic_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_semantic_chunk: %s\n" % e)
```
** Request that uses various inputs **

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
    create_semantic_chunks_request = CreateSemanticChunksRequest(
        text="Biology is the study of living organisms and their interactions with the environment. Biology encompasses various fields such as genetics, ecology, and physiology to understand the structure, function, and behavior of life forms. Cells serve as the fundamental units of life, carrying out essential processes like metabolism and reproduction. Biological research contributes to advancements in medicine, agriculture, and conservation. Economics examines the allocation of resources to meet the needs and wants of individuals and societies. It analyzes the behavior of consumers, producers, and governments in shaping markets and determining prices. Key concepts like supply and demand, inflation, and unemployment help evaluate economic performance. Micro economics focuses on individual choices, while macro economics studies the broader economy. Understanding economics is vital for creating policies that foster growth and address issues like poverty and inequality. Physics studies the fundamental forces and laws governing the natural world. It explores concepts such as motion, energy, and matter, from the smallest particles to the vastness of space. Theories like relativity and quantum mechanics challenge the understanding of time, space, and reality. Physics drives technological advancements, including innovations in electricity and space exploration. The principles of physics help explain everything from everyday phenomena to the workings of the universe.", 
        text_splitting_strategy=text_splitting_strategy, # SENTENCE_DISAMBIGUATION is default, can also be SENTENCE_DELIMITER
        combining_strategy=combining_strategy, # ADJACENT_LINES is default, can also be SLIDING_WINDOW or TUMBLING_WINDOW
        buffer_size=buffer_size, # determines the size of window with SLIDING_WINDOW or TUMBLING_WINDOW and number of adjacent lines to combine with ADJACENT_LINES
        similarity_strategy=similarity_strategy,
        breakpoint_strategy=breakpoint_strategy, # PERCENTILE is default, can also be STANDARD_DEVIATION, INTERQUARTILE or GRADIENT
        breakpoint_threshold_tuner=breakpoint_threshold_tuner, #Determines the sensitivity of the breakpoint strategy
        maximum_chunk_size=maximum_chunk_size #After semantic chunking, if the resulting chunk sizes are bigger than this, the chunks will be broken further.
    )

    try:
        create_semantic_chunk_response = client.data.create_semantic_chunks(
            create_semantic_chunks_request=create_semantic_chunks_request)
        print("The response of DataApi->create_semantic_chunk:\n")
        pprint(f"created {create_semantic_chunk_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_semantic_chunk: %s\n" % e)
```

# create_fixed_size_chunks
** Request that uses various inputs **

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
        chunk_size=chunk_size, #The target size of each text chunk in tokens.
        min_chunk_size_chars=min_chunk_size_chars, #The minimum size of each text chunk in characters.
        min_chunk_length_to_embed=min_chunk_length_to_embed, #The minimum length of a chunk to be included.
        max_num_chunks=max_num_chunks, #The maximum number of chunks to generate from a text.
        keep_separator=keep_separator #Whether to keep separators (like newlines) in the chunks
    )

    try:
        create_fixed_size_chunks_response = client.data.create_fixed_size_chunks(
            create_fixed_size_chunks_request=create_fixed_size_chunks_request)
        print("The response of DataApi->create_fixed_size_chunks_response:\n")
        pprint(f"created {create_fixed_size_chunks_response}")
    except ApiException as e:
        print("Exception when calling DataApi->create_fixed_size_chunks_response: %s\n" % e)
```