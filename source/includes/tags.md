# Tags

Tags are categories or techniques used in the creation of the code fragment.

## Get list of Tags

```shell
curl "localhost:8080/api/v1/fragments/tags"
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "label": "string"
    },
    {
        "id": 2,
        "label": "recursive"
    },
    {
        "id": 3,
        "label": "linked list"
    },
    {
        "id": 4,
        "label": "binary tree"
    }
]
```

This endpoint performs a query to retrieve the list of tags from the database.

### HTTP Request

`GET localhost:8080/api/v1/fragments/tags`
