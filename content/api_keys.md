## API Keys

This is API keys documentation. You can use this API to request
for details on API keys.

### Check API calls limit

Check API calls limit left

```endpoint
GET /v1/api_keys
```

#### Example request

```curl
$ curl https://api.filescan.dev/v1/api_keys
```

#### Example response

```json
{
    "data": {
        "attributes": {
            "limit_left": 9,
            "secret_key": "sk_fcca1eb92d8452962fcf2d8905f4f5ef"
        },
        "id": "1",
        "relationships": {
            "project": {
                "data": {
                    "id": "1",
                    "type": "project"
                }
            },
            "user": {
                "data": {
                    "id": "1",
                    "type": "user"
                }
            }
        },
        "type": "api_key"
    }
}

```


