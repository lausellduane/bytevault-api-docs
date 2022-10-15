# Programming Languages

## Get list of programming languages

```shell
curl "localhost:8080/api/v1/programming-languages"
```

> The above command returns JSON structured like this:

```json
[
    {
        "id": 1,
        "label": "JavaScript"
    },
    {
        "id": 2,
        "label": "Python"
    },
    {
        "id": 3,
        "label": "Golang"
    }
]
```

This endpoint performs a query to retrieve the list of programming languages from the database.

### HTTP Request

`GET localhost:8080/api/v1/programming-languages`
