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
        for dataset in get_datasets_response.protean_datasets:
            pprint(f"retrieved {get_datasets_response.id}")
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
# add_file_datasource
```python
import os
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    file = (
        "test-file-name", # Name under which the file will be stored in the Dataset 
        open("./test-file-name.txt", "rb").read() # File content in either binary or string format
    )
    try:
        client.dataset.add_file_datasource(id="7450d6eb-bf50-422c-a9ff-fd57c3b524ad", file=file)
        print("Executed DatasetApi->add_file_datasource.")
    except ApiException as e:
        print("Exception when calling DatasetApi->add_file_datasource: %s\n" % e)
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