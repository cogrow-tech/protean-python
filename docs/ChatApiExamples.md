# question
Generate RAG enabled model response for the provided prompt.

**Base request that includes foundational configuration parameters**
```python
import os
from pprint import pprint
from protean import Protean, ApiException, ChatQuestionRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    chat_question_request = ChatQuestionRequest(
        model="llama-3.2-1b-instruct",
        systemMessage="You are Protean, a friendly, helpful, kind and good at writing chatbot.",
        userMessage="Write hello world in python",
        temperature=0.1, # This is the default and can be omitted.
        datasets=["*"], # Include all datasets available to you. Otherwise provide dataset GUIDs to include only specific datasets.
        limit=3, # This is the default and can be omitted.
        relevanceThreshold=0.8  # This is the default and can be omitted.
    )
    
    try:
        chat_question_response = client.chat.question(chat_question_request=chat_question_request)
        print("The response of ChatApi->question:\n")
        pprint(chat_question_response)
    except ApiException as e:
        print("Exception when calling ChatApi->question: %s\n" % e)
```

**Assistant based request where model, system message, temperature and datasets values are taken from the Assistant configuration**
```python
import os
from pprint import pprint
from protean import Protean, ApiException, ChatQuestionRequest

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    chat_question_request = ChatQuestionRequest(
        userMessage="Write hello world in python",
        assistantId="d0201a23-e04f-4269-b252-648120fd81df",
        limit=3,  # This is the default and can be omitted.
        relevanceThreshold=0.8  # This is the default and can be omitted.
    )
    
    try:
        chat_question_response = client.chat.question(chat_question_request=chat_question_request)
        print("The response of ChatApi->question:\n")
        pprint(chat_question_response)
    except ApiException as e:
        print("Exception when calling ChatApi->question: %s\n" % e)
```

**Request that generates tool input response**
```python
import os
from pprint import pprint
from protean import Protean, ApiException, ChatQuestionRequest, ClientTools, ClientToolDefinition

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    client_tools = ClientTools(parallelCalls=True, definitions=[
        ClientToolDefinition(
            name="get_current_weather",
            description="Get current weather",
            inputSchema={
                "type": "object",
                "properties": {
                    "location": {
                        "type": "string",
                        "description": "The city and country, eg. San Francisco, USA"
                    },
                    "format": {
                        "type": "string",
                        "enum": [
                            "celsius",
                            "fahrenheit"
                        ]
                    }
                },
                "required": [
                    "location",
                    "format"
                ]
            }
        ),
        ClientToolDefinition(
            name="get_current_time",
            description="Get the current time",
            inputSchema={
                "type": "object",
                "properties": {
                    "location": {
                        "type": "string",
                        "description": "The city and country, eg. San Francisco, USA"
                    }
                },
                "required": [
                    "location"
                ]
            }
        )
    ])
    
    chat_question_request = ChatQuestionRequest(
        model="llama-3.2-1b-instruct",
        systemMessage="You are Protean, a friendly, helpful, kind and good at writing chatbot.",
        userMessage="What is the time and weather in Eindhoven?",
        clientTools=client_tools
    )
    
    try:
        chat_question_response = client.chat.question(chat_question_request=chat_question_request)
        print("The response of ChatApi->question:\n")
        pprint(chat_question_response)
    except ApiException as e:
        print("Exception when calling ChatApi->question: %s\n" % e)
```
