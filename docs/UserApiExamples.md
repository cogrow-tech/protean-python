# get_user_profile
```python
import os
from pprint import pprint
from protean import Protean, ApiException

with Protean(base_url=os.environ.get("PROTEAN_BASE_URL"), api_key=os.environ.get("PROTEAN_API_KEY")) as client:
    user = client.user.get_user_profile()

    try:
        user = client.user.get_user_profile()
        print("The response of UserApi->user:\n")
        pprint(user)
    except ApiException as e:
        print("Exception when calling ChatApi->question: %s\n" % e)
```
