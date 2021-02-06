# Assets

## List assets

```shell
TOKEN="my-super-secret-token"
curl "https://kf.kobotoolbox.org/api/v2/assets/?format=json" \
  -H "Authorization: Token $TOKEN"
```

```python
import requests

URL = 'https://kf.kobotoolbox.org/api/v2/assets'
TOKEN = 'my-super-secret-token'

headers = {'Authorization': f'Token {TOKEN}'}
params = {'format': 'json'}
res = requests.get(URL, headers=headers, params=params)
data = res.json()
```

> The above command returns JSON structured like this:

```json
{
  "count": 1,
  "next": null,
  "previous": null,
  "results": [
    {
      "url": "http://kf.kobotoolbox.org/api/v2/assets/aUNYdrhtbPvL6YijTEhWrB/?format=json",
      "date_modified": "2021-02-03T19:12:20.313279Z",
      "date_created": "2021-02-03T19:12:09.332893Z",
      "owner": "http://kf.kobotoolbox.org/api/v2/users/username/?format=json",
      "summary": {...},
      "owner__username": "username",
      "parent": null,
      "uid": "aUNYdrhtbPvL6YijTEhWrB",
      "tag_string": "",
      "settings": {...},
      "kind": "asset",
      "name": "Foo Form",
      "asset_type": "survey",
      "version_id": "vKcfB9YcP9fZJZzos9haFb",
      "has_deployment": true,
      "deployed_version_id": "vKcfB9YcP9fZJZzos9haFb",
      "deployment__identifier": "http://kc.kobotoolbox.org/username/forms/aUNYdrhtbPvL6YijTEhWrB",
      "deployment__active": true,
      "deployment__submission_count": 1,
      "permissions": [...],
      "export_settings": [...],
      "downloads": [...],
      "data": "http://kf.kobotoolbox.org/api/v2/assets/aUNYdrhtbPvL6YijTEhWrB/data/?format=json",
      "subscribers_count": 0,
      "status": "shared",
      "access_types": null,
      "children": {
        "count": 0
      }
    }
  ]
}
```

This endpoint retrieves all assets that you have permission to view.

### HTTP Request

`GET http://kf.kobotoolbox.org/api/v2/assets/`

### Query Parameters

Parameter | Default | Options |  Description
--- | --- | --- | ---
format | json | json, xml | Renders the response to the specified format
limit | 300 | <30,000 | Limits the number of assets returned
q | | refer to xxx | Filters the returned data based on specified search parameters

## Get a Specific Asset

```shell
TOKEN="my-super-secret-token"
curl "https://kf.kobotoolbox.org/api/v2/assets/aXsfJfSfvJw3gdvs/?format=json" \
  -H "Authorization: Token $TOKEN"
```

```python
import requests

BASE_URL = 'https://kf.kobotoolbox.org/api/v2/assets'
TOKEN = 'my-super-secret-token'
ASSET_UID = 'aXsfJfSfvJw3gdvs'
URL = f'{BASE_URL}/{ASSET_UID}'

headers = {'Authorization': f'Token {TOKEN}'}
params = {'format': 'json'}
res = requests.get(URL, headers=headers, params=params)
data = res.json()
```

> The above command returns JSON structured like this:

```json
{
  "url": "http://kf.kobotoolbox.org/api/v2/assets/aUNYdrhtbPvL6YijTEhWrB/?format=json",
  "owner": "http://kf.kobotoolbox.org/api/v2/users/username/?format=json",
  "owner__username": "username",
  "parent": null,
  "settings": {...},
  "asset_type": "survey",
  "date_created": "2021-02-03T19:12:09.332893Z",
  "summary": {...},
  "date_modified": "2021-02-03T19:12:20.313279Z",
  "version_id": "vKcfB9YcP9fZJZzos9haFb",
  "version__content_hash": "e705ab3d43194d4d2c5d84e67727b9cbe82d1af4",
  "version_count": 2,
  "has_deployment": true,
  "deployed_version_id": "vKcfB9YcP9fZJZzos9haFb",
  "deployed_versions": {...},
  "deployment__identifier": "http://kc.kobotoolbox.org/username/forms/aUNYdrhtbPvL6YijTEhWrB",
  "deployment__links": {...},
  "deployment__active": true,
  "deployment__data_download_links": {...},
  "deployment__submission_count": 1,
  "report_styles": {...},
  "report_custom": {},
  "map_styles": {},
  "map_custom": {},
  "content": {...},
  ...
  "assignable_permissions": [...],
  "permissions": [...],
  "export_settings": [...],
  "data": "http://kf.kobotoolbox.org/api/v2/assets/aUNYdrhtbPvL6YijTEhWrB/data/?format=json",
  "children": {
    "count": 0
  },
  "subscribers_count": 0,
  "status": "shared",
  "access_types": null
}
```

This endpoint retrieves a specific asset.

### HTTP Request

`GET http://kf.kobotoolbox.org/api/v2/assets/<asset_uid>/`

### URL Parameters

Parameter | Description |
--------- | ----------- |
asset_uid | The `uid` of the asset to retrieve

### Query Parameters

Parameter | Default | Options |  Description
--- | --- | --- | ---
format | json | json, xml | Renders the response to the specified format
limit | 300 | <30,000 | Limits the number of assets returned
q | | refer to xxx | Filters the returned data based on specified search parameters

