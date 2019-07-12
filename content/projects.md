## Projects

This is projects API documentation. You can use this API to request
for details and remove different projects.

### List projects

Lists all scans for a particular account.

```endpoint
GET /v1/projects
```

#### Example request

```curl
$ curl https://api.filescan.dev/v1/projects
```

#### Example response

```json
{
    "data": [
        {
            "attributes": {
                "api_limit": 20,
                "name": "test",
                "usage_count": 11
            },
            "id": "1",
            "relationships": {
                "user": {
                    "data": {
                        "id": "1",
                        "type": "user"
                    }
                }
            },
            "type": "project"
        }
    ]
}

```

### Retrieve a project

Returns a single project.

```endpoint
GET /v1/projects/{project_id}
```

Retrieve information about an existing project.

#### Example request

```curl
curl https://api.filescan.dev/v1/{project_id}
```

#### Example response

```json
{
    "data": {
        "attributes": {
            "api_limit": 20,
            "name": "test",
            "usage_count": 11
        },
        "id": "1",
        "relationships": {
            "user": {
                "data": {
                    "id": "1",
                    "type": "user"
                }
            }
        },
        "type": "project"
    }
}
```

### Update a project

Updates the properties of a particular project.

```endpoint
PATCH /v1/projects/{project_id}
```

#### Example request

```curl
curl --request PATCH https://api.filescan.dev/v1/projects/{project_id} \
  -d @data.json
```

#### Example request body

```json
{
  "name": "foo",
}
```

Property | Description
---|---
`name` | (optional) the name of the project

#### Example response

```json
{
    "data": {
        "attributes": {
            "api_limit": 20,
            "name": "foo",
            "usage_count": 11
        },
        "id": "1",
        "relationships": {
            "user": {
                "data": {
                    "id": "1",
                    "type": "user"
                }
            }
        },
        "type": "project"
    }
}

```

### List scans

List all the scans in a project. The response body will be a
ScanCollection.

```endpoint
GET /v1/projects/{project_id}/scans
```

#### Example request

```curl
curl https://api.filescan.dev/v1/projects/{project_id}/scans
```

#### Example response

```json
{
    "data": [
        {
            "attributes": {
                "created_at": "2019-07-12T09:24:15.475Z",
                "filename": "index.html",
                "scan_details": null,
                "status": "OK"
            },
            "id": "17",
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
            "type": "scan"
        }
    ]
}

```

### Retrieve a scan

Retrieves a scan in a project.

```endpoint
GET /v1/projects/{project_id}/scans/{scan_id}
```

#### Example request

```curl
curl https:///api.filescan.dev/v1/projects/{project_id}/scans/{scan_id}
```

#### Example response

```json
{
    "data": {
        "attributes": {
            "created_at": "2019-07-12T09:24:15.475Z",
            "filename": "index.html",
            "scan_details": null,
            "status": "OK"
        },
        "id": "17",
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
        "type": "scan"
    }
}
```

