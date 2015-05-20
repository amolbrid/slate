## HTTP Response codes

### Successful Responses

Status Code | Description
---------- | -----------
200 | Ok -- Request succeeded
201 | Created -- Resource created successfully

### Error Responses


> 400, 404 and 422 provides more details on error. JSON structure of error response returned for these status codes is in following format:

```json
{
  "message": "",
  "errors": [
    {
      "field": "",
      "messages": [
        "",
        ""
      ]
    }
  ]
}
```

> **errors** attribute in JSON response is optional and is only populated when there are validation errors. Examples:

```
HTTP/1.1 404 Not Found
```

```json
{
  "message":"Couldn't find Advertiser with 'id'=34567"
}
```

```
---

HTTP/1.1 422 Unprocessable Entity
```
```json
{
  "message": "Validation errors",
  "errors": [
    {
      "field": "name",
      "messages": [
        "Name can't be blank"
      ]
    }
  ]
}
```

```
---

HTTP/1.1 400 Bad Request
```
```json
{
  "message": "JSON parsing error: 795: unexpected token at '{\"name\":\"\"'"
}
```

Status Code | Description
---------- | -------
400 | Bad Request -- Unable to understand or parse request
401 | Unauthorized -- Request is either missing API key or API key is invalid.
404 | Not Found -- The specified resource does not exist.
422 | Unprocessable Entity -- Request failed due to validation errors. Validate params and try again.
500 | Internal Server Error -- We had a problem with our server. Try again later.
