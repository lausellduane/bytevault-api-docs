# Code Fragments

## Get Fragments List

```shell
curl "localhost:8080/api/v1/fragments"
```

> The above command returns JSON structured like this:

```json
[
    {
        "_id": "631fe20e9265dfc6c8be80aa",
        "title": "Add Binary",
        "description": "Given two binary strings (strings containing only 1s or 0s) return their sum (also as a binary string).",
        "notes": "Neither binary string will contain leading 0s unless the string itself is 0.",
        "value": "let s1 = \"100\";\nlet s2 = \"1\";\nlet s3 = \"11\";\nlet s4 = \"1\";\nlet s5 = \"1\";\nlet s6 = \"0\";\n\nfunction addBinary(s1, s2){\nconsole.log(\"s1: \" + s1);\nconsole.log(\"s2: \" + s2);\nlet d1 = parseInt(s1, 2);\n  console.log(\"d1: \" + d1);\n  let d2 = parseInt(s2, 2);\n  console.log(\"d2: \" + d2);\n  let sum = d1 + d2;\n  console.log(\"sum: \" + sum);\n  \n  return sum.toString(2) \n}\n\nconsole.log(\"addBinary: \" + addBinary(s5, s6));",
        "tags": [
            {
                "id": 1,
                "label": "string"
            }
        ],
        "language": 1
    },
    {
        "_id": "631fe20e9265dfc6c8be80a6",
        "title": "Reverse String",
        "description": "Given a string , reverse all of its characters and return the resulting string.","notes": "",
        "value": "let s = \"civic\";\n\nfunction reverseString(s){\n  let s_arr = s.split(\"\");\n  console.log(\"s_arr: \" + s_arr);\n  let new_s_arr = [];\n  for(let i = s_arr.length - 1; i \u003e= 0; i--){\n    new_s_arr.push(s_arr[i]);\n  }\n  console.log(\"new_s_arr: \" + new_s_arr);\n  return new_s_arr.join(\"\");\n}\nlet result = reverseString(s);\nconsole.log(\"result: \" + result);\n\nfunction isPalindrome(s){\nlet reverse = reverseString(s);\n  if (s == reverse){\n  return true;\n  }\n  return false;\n}",
        "tags":[
            {
                "id": 1,
                "label": "string"
            }
        ],
        "language": 1
    }
]
```

This endpoint performs a query to retrieve the list of code fragments from the database.

### HTTP Request

`GET localhost:8080/api/v1/fragments`

## Create Fragment

```shell
curl -X POST \
  -H "Content-Type: application/json" \
  -d '{
	"title":"curl fragment",
    "description":"this fragment was created through curl",
	"notes":"these are some notes about curl",
	"value":"localhost:8080/api/v1/fragments",
	"tags":[{
                "id":1,
                "label":"string"
            }],
	"language":2
}' \
  "localhost:8080/api/v1/fragments"
```

> The above command returns JSON structured like this:

```json
{
    "InsertedID": "63431398f0942bee7e102d0c"
}
```

This endpoint creates a new code fragment.

### HTTP Request

`POST localhost:8080/api/v1/fragments`

### Request Body

Key | Required | Description | Type
--- | -------- | ----------- | ----
title | `true` | Name for code fragment | `string`
description | `true` | Description for code fragment | `string`
notes | `false` | Additional information associated with the code fragment | `string`
value | `true` | Code fragment value | `string`
tags | `true` | List of tags associated with the code fragment | `array`
language | `true` | Programming language for the code fragment | `int`

## Delete Code Fragment

```shell
curl -X DELETE \
  -H "Content-Type: application/json" \
  -d '{
	"id": "63431398f0942bee7e102d0c"
}' \
  "localhost:8080/api/v1/fragments"
```

> The above command returns JSON structured like this:

```json
"63431398f0942bee7e102d0c"
```


This endpoint deletes an code fragment from the database.

### HTTP Request

`DELETE localhost:8080/api/v1/fragments`

### Request Body

Key | Required | Description | Type
--- | -------- | ----------- | ----
id | `true` | MongoDB document id for the code fragment | `string`
