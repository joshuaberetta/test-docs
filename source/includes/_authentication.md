# Authentication

> To authorize, use this code:

```shell
# Within the shell, you can get your API token by doing the following:
curl -u username:password "https://kf.kobotoolbox.org/token/?format=json"
```

```python
import requests
from requests.auth import HTTPBasicAuth

# Ensure you are using the correct kobo server
URL = "https://kf.kobotoolbox.org/token"

params = {'format': 'json'}
res = requests.get(
    URL, auth=HTTPBasicAuth('username', 'password'), params=params
)
data = res.json()
token = data['token']
```


> Make sure to replace `username` and `password` with your username and password.

All requests to `/api/v2` endpoints require an authorization header
with the token obtained above.

`Authorization: Token TOKEN`

<aside class="notice">
You must replace <code>TOKEN</code> with your personal access token.
</aside>

