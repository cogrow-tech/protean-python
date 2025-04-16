# Search
Search for vector documents that closely match provided query. Service utilizes both hybrid search and reranking to
retrieve the best possible match.

```python
import os
from pprint import pprint
from protean import Protean, ApiException, VectorSearchRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    vector_search_request = VectorSearchRequest(
        query="What are the company security policies for handling data?",
        resourceIds=["840a228d-a718-40b7-9ac5-b0a716b3896b"],  # Existing dataset GUIDs to query against.
        limit=3,  # This is the default and can be omitted.
        relevanceThreshold=0.8  # This is the default and can be omitted.
    )
    try:
        vector_search_response = client.vector.search(vector_search_request=vector_search_request)
        print(vector_search_response.documents)
        print("The response of VectorApi->search:\n")
        pprint(vector_search_response.documents)
    except ApiException as e:
        print("Exception when calling VectorApi->search: %s\n" % e)
```